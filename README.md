<img src="public/logo_sc.png" alt="SteelCook logo" width="220" />

# SteelCook

Landing page minimal construida con Vite + TypeScript para presentar la marca SteelCook y canalizar contactos vía WhatsApp.

## Tabla de contenidos
- **[Demo / Producción](#demo--producción)**
- **[Tecnologías](#tecnologías)**
- **[Características](#características)**
- **[Requisitos](#requisitos)**
- **[Instalación y uso](#instalación-y-uso)**
- **[Estructura del proyecto](#estructura-del-proyecto)**
- **[Personalización](#personalización)**
- **[Despliegue](#despliegue)**
- **[Licencia](#licencia)**

## Demo / Producción
- Dominio: `https://steelcook.com.co`

## Tecnologías
- Vite `^7` (bundler y servidor de desarrollo)
- TypeScript `~5.8`
- HTML/CSS vanilla
- gh-pages para despliegue a GitHub Pages

## Características
- **Landing responsive** con fondo y blur.
- **Logo ajustable** (ver clase `logo` en `src/style.css`).
- **CTA a WhatsApp** directo con ícono SVG.
- **Assets estáticos** en `public/` (favicon, background, logo, svg).

## Requisitos
- Node.js >= 18
- npm (se incluye `package-lock.json`)

## Instalación y uso
```bash
# 1) Instalar dependencias
npm install

# 2) Ambiente de desarrollo (hot reload)
npm run dev

# 3) Compilar a producción
npm run build

# 4) Previsualizar build local
npm run preview
```

Scripts disponibles (`package.json`):
- `dev`: Vite dev server
- `build`: `tsc && vite build`
- `preview`: `vite preview`
- `deploy`: `gh-pages -d dist`

## Estructura del proyecto
```text
.
├─ index.html                 # Punto de entrada HTML
├─ public/                    # Activos estáticos servidos tal cual
│  ├─ steelcook.svg           # Favicon
│  ├─ logo_sc.png             # Logo principal
│  ├─ bg.jpg                  # Imagen de fondo
│  └─ CNAME                   # Dominio para GitHub Pages (steelcook.com.co)
├─ src/
│  ├─ main.ts                 # Lógica de UI (creación del DOM)
│  └─ style.css               # Estilos principales (variables y responsive)
├─ vite.config.js             # `base: './'` para rutas relativas en Pages
├─ tsconfig.json              # Configuración TypeScript
└─ package.json               # Scripts y devDependencies
```

## Personalización
- **Textos**: editar los strings en `src/main.ts` (`titleString`, `paragraphString1`, `paragraphString2`).
- **WhatsApp**: actualizar el número en `src/main.ts` (`whatsapp.href = "https://wa.me/57XXXXXXXXXX"`).
- **Logo**: reemplazar `public/logo_sc.png` y el tamaño vía CSS en `.logo` (`src/style.css`).
- **Fondo**: sustituir `public/bg.jpg` y ajustar `#app { background-image: ... }` en `src/style.css`.
- **Favicon**: `index.html` referencia `steelcook.svg` en `public/`.

## Despliegue
Este repo está preparado para GitHub Pages.

1. Ejecuta el build:
   ```bash
   npm run build
   ```
2. Publica el contenido de `dist/` a la rama `gh-pages` con:
   ```bash
   npm run deploy
   ```
3. El archivo `public/CNAME` fija el dominio a `steelcook.com.co`.
4. Asegúrate de que Pages apunte a la rama `gh-pages` en la configuración del repositorio.

Nota: `vite.config.js` define `base: './'` para que los assets funcionen correctamente en Pages.

## Licencia
Propietario. Todos los derechos reservados. Actualiza esta sección si deseas usar una licencia abierta (por ejemplo, MIT).
