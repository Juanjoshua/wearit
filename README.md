# WEARIT — Guía de despliegue para fase de pruebas

## Archivos del proyecto

```
wearit/
├── index.html                    ← App completa
├── manifest.json                 ← Configuración PWA
├── sw.js                         ← Service Worker (modo offline)
├── netlify.toml                  ← Configuración Netlify
└── netlify/
    └── functions/
        └── claude.js             ← Servidor seguro para la IA
```

---

## PASO 1 — Crear cuenta en GitHub (gratis)

1. Entra a https://github.com
2. Crea una cuenta gratuita
3. Crea un repositorio nuevo llamado `wearit`
4. Sube todos los archivos de esta carpeta

---

## PASO 2 — Obtener API Key de Anthropic (gratis para empezar)

1. Entra a https://console.anthropic.com
2. Crea una cuenta
3. Ve a "API Keys" → "Create Key"
4. Copia la key — se ve así: `sk-ant-api03-...`
5. Guárdala en un lugar seguro, la necesitas en el paso 4

---

## PASO 3 — Crear cuenta en Netlify (gratis)

1. Entra a https://netlify.com
2. Crea una cuenta con tu email
3. Conecta tu cuenta de GitHub

---

## PASO 4 — Desplegar en Netlify

1. En Netlify: "Add new site" → "Import an existing project"
2. Selecciona GitHub → elige el repositorio `wearit`
3. En "Build settings":
   - Build command: (dejar vacío)
   - Publish directory: `.`
4. Click "Deploy site"
5. Espera ~1 minuto — Netlify genera tu link: `wearit-xxxxx.netlify.app`

---

## PASO 5 — Agregar la API Key de forma segura

1. En Netlify, ve a: Site settings → Environment variables
2. Click "Add a variable"
3. Key: `ANTHROPIC_API_KEY`
4. Value: pega tu API Key (`sk-ant-api03-...`)
5. Click "Save"
6. Ve a "Deploys" → "Trigger deploy" → "Deploy site"

¡Listo! La IA ya funciona de forma segura.

---

## PASO 6 — Compartir para pruebas

Tu link de prueba será algo como:
`https://wearit-beta.netlify.app`

Puedes cambiar el nombre en: Site settings → Domain management → Options → Edit site name

Compártelo por WhatsApp con tus testers:
> "Hola! Estoy probando una app nueva que se llama WEARIT — el estilista que te dice la verdad. ¿Me darías tu opinión honesta? Solo abre este link desde tu teléfono: https://wearit-beta.netlify.app"

---

## Preguntas para recopilar feedback

Después de que prueben la app, pregúntales:

1. ¿La usarías todos los días? ¿Por qué sí o no?
2. ¿Qué fue lo que más te gustó?
3. ¿Qué le falta o cambiarías?
4. ¿Le recomendarías la app a alguien? ¿A quién?
5. ¿El tono directo de WEARIT te parece bien o incómodo?

---

## Costo estimado fase de pruebas

| Servicio | Costo |
|----------|-------|
| GitHub | Gratis |
| Netlify | Gratis |
| Anthropic API (50-100 usuarios probando) | ~$1-3 USD |
| **Total** | **~$2 USD** |

---

## Próximos pasos después del feedback

1. Recopilar opiniones (1-2 semanas)
2. Priorizar mejoras con Claude
3. Versión final pulida
4. Publicar en Play Store ($25 USD una sola vez)
