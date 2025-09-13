# Retro Computer Personal Website

https://edh.dev/ (formerly edwardh.io)

This project is a 3D interactive retro computer portfolio website, built with TypeScript, [THREE.js](https://threejs.org/), and Vite. It features a custom UNIX-like shell, a virtual file system, markdown rendering, and a text layout engine, all running in the browser.

---

## Project Structure

```
.
├── .gitignore
├── index.html
├── LICENSE.MD
├── package.json
├── README.md
├── tsconfig.json
├── vite.config.ts
├── public/
│   ├── _redirects
│   ├── .gitkeep
│   ├── manifest.json
│   ├── fonts/
│   │   ├── chill.json
│   │   ├── chill.woff
│   │   ├── public-pixel.json
│   │   └── public-pixel.woff
│   ├── icon/
│   │   └── ... (various PNG icons)
│   └── images/
│       └── ... (project images)
├── models/
│   └── ... (3D model files)
├── textures/
│   └── ... (texture files)
└── src/
    ├── collapse.css
    ├── DeltaTime.js / DeltaTime.ts
    ├── main.css
    ├── main.ts
    ├── nav.css
    ├── vite-env.d.ts
    ├── file-system/
    │   └── home/user/...
    ├── img/
    ├── terminal/
    │   ├── applications/
    │   │   ├── applications.ts
    │   │   ├── cd.ts
    │   │   ├── echo.ts
    │   │   ├── hello.ts
    │   │   ├── index.ts
    │   │   ├── ls.ts
    │   │   ├── mkdir.ts
    │   │   ├── pwd.ts
    │   │   ├── show.ts
    │   │   └── touch.ts
    │   ├── bash.ts
    │   ├── fileSystemBash.ts
    │   └── index.ts
    ├── webgl/
    │   ├── index.ts
    │   ├── loader.ts
    │   └── screen/
    │       ├── index.ts
    │       ├── lag.ts
    │       ├── renderEngine.ts
    │       ├── shaderToScreen.ts
    │       └── textEngine.ts
    └── ...
```

---

## Folder & File Overview

### Root Files

- **index.html**: Main HTML entry point, includes the canvas and UI elements.
- **package.json**: Project dependencies and scripts.
- **tsconfig.json**: TypeScript configuration.
- **vite.config.ts**: Vite build and dev server configuration.
- **README.md**: This documentation.
- **LICENSE.MD**: MIT License.

### `public/`

- **fonts/**: Bitmap fonts used for terminal and UI rendering.
- **icon/**: App icons for PWA and social previews.
- **images/**: Static images for project showcases.
- **manifest.json**: PWA manifest.

### `models/` and `textures/`

- 3D models and textures for the retro computer and scene.

### `src/`

#### Top-level

- **main.ts**: Entry point, initializes the WebGL scene and event listeners.
- **main.css**, **nav.css**, **collapse.css**: Stylesheets for layout and UI.
- **DeltaTime.ts/js**: Utility for frame delta timing.
- **vite-env.d.ts**: Vite type definitions.

#### `file-system/`

- Contains the virtual file system content, including markdown files for "about", "projects", etc. These are loaded and rendered in the terminal.

#### `img/`

- Additional images used in the UI or 3D scene.

#### `terminal/`

Implements the UNIX-like shell and file system logic:

- **index.ts**: Main terminal logic, input handling, and integration with the screen text engine.
- **bash.ts**: Command parsing and execution.
- **fileSystemBash.ts**: Virtual file system implementation, including navigation and file/folder creation.
- **applications/**: Built-in shell commands:
  - `ls`, `cd`, `pwd`, `mkdir`, `touch`, `echo`, `show`, `hello`: Each file implements a shell command.
  - `applications.ts`: Registers and exposes all commands.

#### `webgl/`

Handles 3D rendering and the virtual computer:

- **index.ts**: Sets up the 3D scene, camera, controls, and animation loop.
- **loader.ts**: Loads 3D models, textures, and fonts.
- **screen/**: Renders the CRT screen:
  - **index.ts**: Integrates the render and text engines.
  - **renderEngine.ts**: Handles post-processing, shaders, and effects.
  - **shaderToScreen.ts**: Utility for rendering shaders to the screen.
  - **lag.ts**: Implements a lag effect for CRT simulation.
  - **textEngine.ts**: Renders text, markdown, and manages the terminal display.

---

## Key Features

- **3D Retro Computer**: Interactive model rendered with THREE.js.
- **UNIX-like Shell**: Type commands (`ls`, `cd`, `show`, etc.) to explore the virtual file system.
- **Virtual File System**: Markdown and images are loaded as files, simulating a real OS.
- **Markdown Rendering**: Custom markdown parser and renderer for project and about pages.
- **Text Layout Engine**: Custom engine for text rendering and layout on the CRT screen.
- **Custom Shaders**: CRT and bloom effects for authentic retro visuals.
- **Responsive UI**: Works on desktop and mobile, with PWA support.

---

## Build & Run Instructions

```bash
# Install dependencies (only the first time)
npm install

# Run the local server at localhost:1234
npm run dev

# Build for production in the dist/ directory
npm run build
```

---

## Credits

- Developed and designed by Ed Hinrichsen.
- Computer model based on the Commodore PET 8296.
- MIT License.

---

