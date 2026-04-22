# Fuera del Marco

Blog personal hecho con Astro. La idea del sitio es publicar textos (Markdown) con una estructura sencilla: portada, listado de posts, post individual, una página “Sobre mí” y un feed RSS.

## Qué encontrarás

- **Inicio**: portada del sitio.
- **Blog**: listado de artículos.
- **Post**: página individual por artículo (ruta por *slug*).
- **Sobre mí**: página estática.
- **RSS**: feed con las últimas publicaciones.

Los metadatos globales del sitio (título y descripción) viven en `src/consts.ts`.

## Estructura del proyecto

```text
public/              # Archivos estáticos (p. ej. CNAME)
src/
  pages/             # Rutas del sitio (Astro)
  content/blog/      # Posts en Markdown/MDX
  layouts/           # Layouts (p. ej. BlogPost)
  components/        # Header, Footer, etc.
  styles/            # CSS global
```

## Escribir un post

Los posts se guardan en `src/content/blog/` como `.md` o `.mdx`.

El *frontmatter* está validado por Content Collections y debe incluir como mínimo:

```yaml
---
title: "Título del post"
description: "Resumen corto para listados y SEO"
pubDate: 2026-04-22
# Opcionales
updatedDate: 2026-04-23
tags:
  - tag-1
  - tag-2
heroImage: "./ruta/a/imagen" # si aplica
---
```

Notas:

- `pubDate`/`updatedDate` se convierten a `Date` automáticamente.
- `tags` es opcional.
- `heroImage` es opcional (si lo usas, debe ser una imagen válida para Astro).

## Comandos

Desde la raíz del proyecto:

| Comando | Acción |
| --- | --- |
| `npm install` | Instala dependencias |
| `npm run dev` | Arranca el servidor local (`http://localhost:4321`) |
| `npm run build` | Genera el build de producción en `dist/` |
| `npm run preview` | Previsualiza el build |

## Publicación

El proyecto genera un sitio estático. El output está en `dist/` tras `npm run build` (ideal para Netlify, Vercel, GitHub Pages, etc.).
