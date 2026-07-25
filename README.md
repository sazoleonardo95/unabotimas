# Una Botillería a Más — sitio web

## Archivos a subir a GitHub

Sube **toda esta carpeta** tal cual, manteniendo la estructura:

```
una-botilleria/
├── index.html
├── robots.txt
├── sitemap.xml
├── README.md          (opcional, no afecta el sitio)
└── assets/
    └── logo.png
```

No falta ningún archivo — es un sitio estático simple, sin build ni dependencias.

## Antes de subirlo — 2 cosas pendientes

Busca y reemplaza en `index.html`:

1. **Número de WhatsApp** — aparece como `56900000000` en 5 lugares (nav, hero, eventos, contacto, footer, y en el JSON-LD como `+56900000000`). Reemplázalo por tu número real con formato `56912345678` (sin espacios ni +, para los links `wa.me`).
2. **Correo de contacto** — `contacto@unabotilleriaamas.cl` en el footer. Ajústalo si tu dominio o correo real es distinto.

También revisa `sitemap.xml` y `robots.txt`: ambos asumen el dominio `unabotilleriaamas.cl`. Si el dominio final es otro, actualízalos ahí.

## Subir a GitHub (desde cero)

Si el repo aún no existe:

```bash
cd una-botilleria
git init
git add .
git commit -m "Sitio Una Botillería a Más"
git branch -M main
git remote add origin https://github.com/TU-USUARIO/una-botilleria.git
git push -u origin main
```

Si ya tienes el repo creado en GitHub (vacío), reemplaza la URL del `remote add` por la tuya y salta el paso de `git init` si ya existe localmente.

## Deploy en Vercel

1. En [vercel.com](https://vercel.com) → **Add New → Project** → importa el repo de GitHub.
2. Framework preset: **Other** (es HTML estático, no necesita build command).
3. Deploy. Como es una sola página, no necesita `vercel.json` con reglas de rewrite.
4. Conecta tu dominio en **Settings → Domains** cuando lo tengas listo.

## Pendiente para producción real

Las fotos de whisky del catálogo y las secciones de historia son **fotografía de stock (Pexels, uso libre)**, no fotos de tus productos reales. Sirven para mostrar la dirección visual, pero antes de publicar en serio conviene reemplazarlas por fotos propias de las botellas que efectivamente vendes — mejora muchísimo la confianza del cliente y evita mostrar categorías genéricas en vez de tu inventario real.

Para reemplazar una foto del catálogo: en `index.html`, busca la tarjeta correspondiente (`data-cat="scotch"`, `"bourbon"`, `"japones"` o `"chileno"`) y cambia la URL en `data-img` y en el `style="background-image:url(...)"` de `.cat-card__img` por la ruta de tu propia foto (por ejemplo `/assets/scotch-1.jpg`).
