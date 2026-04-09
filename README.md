<<<<<<< HEAD
# Portfolio DevOps — Template

Template base para el ejercicio integrador del curso **Certificado DevOps — ORT ATI**.
Los estudiantes clonan este repositorio, personalizan el portfolio con su información real
y lo despliegan en internet a lo largo de las distintas fases del curso.

## Estructura del proyecto

```text
portfolio-template/
├── index.html                 # Estructura HTML del portfolio
├── style.css                  # Estilos del portfolio
├── theme.js                   # Lógica del toggle dark/light mode
├── theme.test.js              # Tests unitarios (Vitest)
├── package.json               # Dependencias y scripts de Node
├── Dockerfile                 # Imagen para correr el sitio localmente con Docker
├── docker-compose.yml         # Entorno de desarrollo con edición en tiempo real
├── .dockerignore
├── .gitignore
└── ejercicio-integrador.md    # Consigna completa de la Fase 1
```

## Preview

![Portfolio template](screenshot.png)

## Correr localmente

### Desarrollo — edición en tiempo real (recomendado)

Usa `docker-compose.yml`, que monta los archivos del proyecto directamente en el contenedor.
Cada vez que guardás un cambio, alcanza con refrescar el navegador para verlo reflejado — sin reconstruir la imagen.

```bash
docker compose up
```

Abrir `http://localhost:8080`. Para detener: `Ctrl+C`.

### Producción — imagen construida

Construye una imagen autocontenida con los archivos copiados adentro.
Útil para probar el artefacto final antes de hacer un deploy.

```bash
docker build -t portfolio .
docker run --name portfolio -p 8080:80 portfolio
```

### Sin Docker

Abrir `index.html` directamente en el navegador, o usar cualquier servidor HTTP estático:

```bash
# Python
python3 -m http.server 8080

# Node.js (npx)
npx serve .
```

## Personalización

Todos los lugares a editar están marcados con comentarios `<!-- TODO: -->` en `index.html`:

| Qué cambiar | Dónde |
| ----------- | ----- |
| Nombre | `<title>`, nav, hero, footer |
| Rol | `.hero-role` |
| Descripción personal | `.hero-desc` |
| Habilidades técnicas | Sección `#skills` |
| Proyectos | Sección `#projects` |
| Educación | Sección `#education` |
| Contacto | Sección `#contact` |

## Stack del template

- HTML5 + CSS3 (sin frameworks)
- Fuentes: [Syne](https://fonts.google.com/specimen/Syne) + [DM Mono](https://fonts.google.com/specimen/DM+Mono) via Google Fonts
- Servidor: [nginx:alpine](https://hub.docker.com/_/nginx)


