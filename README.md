# IncineroarUI
---

## Versión actual

**v1.0.0** — Primera entrega oficial. Incluye grid system, 7+ componentes UI, helpers y animaciones.
---

> Un Framework CSS personalizado, modular y Mobile First, construido con SASS y arquitectura 7‑1.
> Inspirado en Bootstrap con una paleta de colores candente que usa las tonalidades rojas y negras en representacion de un Incineroar

![versión](https://img.shields.io/badge/version-1.0.0-d62828)
![sass](https://img.shields.io/badge/SASS-modular-ff6a00)
![mobile-first](https://img.shields.io/badge/Mobile_First-✓-22c55e)
![license](https://img.shields.io/badge/license-MIT-3b82f6)

---
## Integrantes del equipo 

- Julio Cesar Aguilar Serrano AS22034
- Jefferson Antonio Vásquez González VG24028
- Abraham Bladimir Umanzor Vásquez UV22001

---

## Descripción

**IncineroarUI** es un sistema de diseño completo desarrollado para el laboratorio de **Herramientas de Productividad** (Universidad de El Salvador, FMO, Ingeniería de Sistemas Informáticos).

Ofrece todo lo necesario para construir interfaces modernas y responsivas sin escribir CSS desde cero:

- Sistema de **rejilla (grid) de 12 columnas** con breakpoints responsivos.
- **Componentes UI** listos para usar: botones, tarjetas, alertas, formularios, navbar, badges y tablas.
- **Clases utilitarias** para tipografía, espaciado, color, flexbox, display y bordes.
- **Animaciones temáticas** con efectos hover, pulse, shake, glow y transiciones suaves.
- Arquitectura **modular SASS** con `@use`, mixins, funciones y mapas iterables.

---

## Paleta de Colores

La paleta combina rojos intensos (marca), un fondo oscuro profundo (lienzo de combate) y colores semánticos para feedback al usuario.

### Colores de Marca

| Variable     | HEX       | Vista                                                                 | Uso                              |
|--------------|-----------|-----------------------------------------------------------------------|----------------------------------|
| `$primary`   | `#d62828` | ![#d62828](https://placehold.co/40x20/d62828/d62828.png)              | Rojo fuego — CTA, branding.      |
| `$secondary` | `#ff6a00` | ![#ff6a00](https://placehold.co/40x20/ff6a00/ff6a00.png)              | Naranja — acento secundario.     |

### Colores Semánticos

| Variable    | HEX       | Vista                                                                 | Uso                          |
|-------------|-----------|-----------------------------------------------------------------------|------------------------------|
| `$success`  | `#22c55e` | ![#22c55e](https://placehold.co/40x20/22c55e/22c55e.png)              | Éxito, confirmaciones.       |
| `$danger`   | `#8b0000` | ![#8b0000](https://placehold.co/40x20/8b0000/8b0000.png)              | Errores, eliminaciones.      |
| `$warning`  | `#f59e0b` | ![#f59e0b](https://placehold.co/40x20/f59e0b/f59e0b.png)              | Advertencias.                |
| `$info`     | `#3b82f6` | ![#3b82f6](https://placehold.co/40x20/3b82f6/3b82f6.png)              | Información, neutral.        |

### Escala de Grises (Tema Oscuro)

| Variable           | HEX       | Vista                                                                 | Uso                              |
|--------------------|-----------|-----------------------------------------------------------------------|----------------------------------|
| `$white`           | `#ffffff` | ![#ffffff](https://placehold.co/40x20/ffffff/ffffff.png)              | Texto en fondos saturados.       |
| `$text-base`       | `#f3f4f6` | ![#f3f4f6](https://placehold.co/40x20/f3f4f6/f3f4f6.png)              | Texto primario.                  |
| `$text-secundario` | `#9ca3af` | ![#9ca3af](https://placehold.co/40x20/9ca3af/9ca3af.png)              | Texto secundario, placeholders.  |
| `$border-base`     | `#3a3a3a` | ![#3a3a3a](https://placehold.co/40x20/3a3a3a/3a3a3a.png)              | Bordes, separadores.             |
| `$bg-surface`      | `#1f1f1f` | ![#1f1f1f](https://placehold.co/40x20/1f1f1f/1f1f1f.png)              | Tarjetas, navbar, footer.        |
| `$bg-base`         | `#0f0f0f` | ![#0f0f0f](https://placehold.co/40x20/0f0f0f/0f0f0f.png)              | Fondo principal de la app.       |

---

## Guía de instalación

Se tienen dos formas de integrar **IncineroarUI** a un proyecto:

### Opción 1 — Vía CDN (recomendado para prototipos)

Coloca este `<link>` dentro del `<head>` de tu HTML:

```html

<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/x-jefferson-2005-x/Framework_CSS_HDP@v1.0.0/css/main.css">




```

### Opción 2 — Descarga local

1. Clona el repositorio:
   ```bash
   git clone https://github.com/x-jefferson-2005-x/Framework_CSS_HDP.git
   ```
2. Copia la carpeta `css/` a tu proyecto.
3. Enlaza el CSS ya compilado en tu HTML:
   ```html
   <link rel="stylesheet" href="./css/main.css" />
   ```
4. (Opcional) Si quieres recompilar tras modificar variables, instala SASS y ejecuta:
   ```bash
   npm install -g sass 
   sass scss/main.scss scss/main.css --watch
   ```

### Estructura mínima de un documento

```html
<!doctype html>
<html lang="es">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>Mi App</title>
    <link rel="stylesheet" href="./css/main.css" />
  </head>
  <body>
    <div class="container my-4">
      <h1 class="fs-1 text-primary">¡Hola IncineroarUI!</h1>
      <button class="btn btn--primary btn--lg">Comenzar</button>
    </div>
  </body>
</html>
```
---

## Arquitectura del proyecto

El framework sigue una arquitectura SASS modular inspirada en el patrón **7‑1** simplificado:

```
scss/
├── abstracts/          # Variables, mixins, funciones — sin output CSS
│   ├── _variables.scss
│   └── _mixins.scss
├── base/               # Reset y tipografía global
│   ├── _reset.scss
│   └── _typography.scss
├── layout/             # Estructura de página
│   ├── _container.scss
│   ├── _grid.scss
│   ├── _header.scss
│   ├── _navbar.scss
│   └── _footer.scss
├── components/         # Componentes UI reutilizables
│   ├── _buttons.scss
│   ├── _cards.scss
│   ├── _alerts.scss
│   ├── _forms.scss
│   ├── _badges.scss
│   └── _tables.scss
├── utilities/          # Clases helper y animaciones
│   ├── _helpers.scss
│   ├── _animationsAlerts.scss
│   ├── _animationsBadges.scss
│   ├── _animationsButtons.scss
│   ├── _animationsCards.scss
│   ├── _animationsForms.scss
│   ├── _animationsNavbars.scss
│   └── _animationsTables.scss
├── main.scss           # Punto de entrada (orquesta @use)
└── main.css            # CSS compilado listo para producción
```

---

## Documentación

La documentación oficial está construida **utilizando IncineroarUI** y desplegada en GitHub Pages:

**[Visitar documentación](https://x-jefferson-2005-x.github.io/Framework_CSS_HDP/)**

Incluye ejemplos de cada componente con su correspondiente bloque de código HTML.

---

## Breakpoints responsivos

| Breakpoint | Ancho mínimo | Dispositivo                     |
|------------|--------------|---------------------------------|
| `sm`       | `576px`      | Móviles en horizontal           |
| `md`       | `768px`      | Tablets                         |
| `lg`       | `992px`      | Laptops y escritorios pequeños  |
| `xl`       | `1280px`     | Pantallas grandes               |

Filosofía **Mobile First**: los estilos base aplican en móvil y se enriquecen progresivamente hacia arriba mediante `@include respond-to($bp)`.

---

## Licencia

Proyecto académico — Universidad de El Salvador, FMO, 2026.
