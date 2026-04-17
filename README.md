# grapesjs-shadcn: A Full-Featured Visual Page Builder Powered by shadcn UI

> Build, style, and publish dynamic pages visually — with a polished shadcn UI, datasource-driven components, and a powerful style manager baked right in.

**[→ Get grapesjs-shadcn on GJS Market](https://gjs.market/products/grapesjs-shadcn)**

> Looking for the code tour?

**[→ Code Tour](./code-tour.md)**

---

## Quickstart

### 1. Open the Project Folder

Clone or download the repository and open the project folder in your terminal.

### 2. Install Dependencies

```bash
npm install
```

### 3. Run the Dev Server

```bash
npm run dev
```

The app is built with **Vite**, **React**, and **shadcn/ui** — so it spins up fast. Open your browser to the local URL shown in the terminal and you're ready to build.

> Don't have the project yet? **[Pick it up on GJS Market](https://gjs.market/products/grapesjs-shadcn)** and get started in minutes.

---

## Feature Overview

### UI Overview

The editor is structured into three key zones:

- **Topbar** — Logo, editable project name, template status toggle, device switcher, undo/redo, project manager, theme switcher (dark/light), clear canvas, grid line toggle, code viewer, data display toggle (resolved data vs. placeholders), preview, and publish.
- **Left Bar** — Panel launchers for Blocks, Layers, Pages, Datasources, Theme, Assets, and Google Fonts.
- **Canvas** — The main editing area with a Rich Text Editor (RTE) toolbar at the top and a right panel housing the Selector Manager, Attributes panel, and Style Manager.

![UI Overview](./screenshots/Screenshot%202026-04-13%20at%2012.34.23.png)

---

### Project Manager

Open or create projects from reusable templates through the Project Manager modal. Templates are published directly from the editor, making it easy to build a library of starting points.

![Project Manager](./screenshots/Screenshot%202026-04-13%20at%2012.34.53.png)

---

### Light & Dark Mode

Switch between light and dark themes from the topbar. The full editor UI adapts, including all panels, modals, and the canvas.

![Light Mode](./screenshots/Screenshot%202026-04-13%20at%2012.35.18.png)

---

### Block Manager

Drag and drop blocks onto the canvas from the left panel. Blocks are organised into sections and are searchable. **Symbols** allow you to create reusable components with shared state across the project.

<img src="./screenshots/Screenshot%202026-04-13%20at%2012.37.14.png" height="500" alt="Block Manager" />

---

### Layer Manager

The layer manager gives you a full tree view of your component hierarchy. Rename layers inline, lock components to prevent accidental edits, delete, and reorder via drag-and-drop.

<img src="./screenshots/Screenshot%202026-04-13%20at%2012.37.55.png" height="500" alt="Layer Manager" />

---

### Page Manager

Manage multi-page projects with ease. Pages can be renamed inline and switched between from the left panel.

<img src="./screenshots/Screenshot%202026-04-13%20at%2012.38.25.png" height="500" alt="Page Manager" />

---

### Datasources

Create dynamic data collections, define their schemas, configure data providers, add manual records, and set up relations between collections — all from the Datasources panel.

![Datasources](./screenshots/Screenshot%202026-04-13%20at%2012.38.51.png)

---

### Theme Manager

Define the default look and feel of your project and manage reusable selectors to keep your design system consistent across pages.

<img src="./screenshots/Screenshot%202026-04-13%20at%2012.39.09.png" height="500" alt="Theme Manager" />

---

### Asset Manager

Drag and drop images directly from the asset panel onto the canvas. Assets are accessible at a glance from the left bar.

<img src="./screenshots/Screenshot%202026-04-13%20at%2012.39.32.png" height="500" alt="Asset Manager" />

---

### Assets Modal

Upload new images or add assets from external URLs through the Assets modal. Manage your full media library in one place.

![Assets Modal](./screenshots/Screenshot%202026-04-13%20at%2012.39.46.png)

---

### Google Fonts

Google Fonts added to the project are listed here and can be removed cleanly — no leftover CSS bloat. Fonts are injected automatically when selected from the style manager.

<img src="./screenshots/Screenshot%202026-04-13%20at%2012.40.25.png" height="500" alt="Google Fonts" />

---

### Selector Manager & Style Manager

The right panel surfaces three key tools:

- **Selector Manager** — Manage CSS classes on the selected component.
- **Attributes** — Edit component attributes, organised into logical categories.
- **Style Manager** — Full control over styles with categorised inputs. Includes all built-in GrapesJS style properties plus custom additions — like the combined padding input that lets you edit all sides at once or detach them for per-side control.

<img src="./screenshots/Screenshot%202026-04-13%20at%2012.41.04.png" height="500" alt="Selector & Style Manager" />

---

### Font Style Input

The font input integrates Google Fonts directly. Selecting a font automatically injects the required CSS into the project — no manual setup needed.

<img src="./screenshots/Screenshot%202026-04-13%20at%2012.42.39.png" height="300" alt="Font Style Input" />

---

### Border Style Input

Border controls include per-side selection — set borders on all sides uniformly or target individual sides independently.

<img src="./screenshots/Screenshot%202026-04-13%20at%2012.43.57.png" height="300" alt="Border Style Input" />

---

### Style Manager Layers

Layered style properties (like box shadows and transitions) are fully supported, with a clean list UI for adding, editing, and reordering multiple values.

<img src="./screenshots/Screenshot%202026-04-13%20at%2012.44.59.png" height="250" alt="Style Manager Layers" />

---

### Rich Text Editor (RTE)

Text components open an inline RTE built on **ProseMirror** with a custom shadcn UI toolbar — giving you a familiar, polished editing experience without leaving the canvas.

![Rich Text Editor](./screenshots/Screenshot%202026-04-13%20at%2012.45.47.png)

---

### Canvas Spots

Interactive canvas spots provide direct manipulation handles for:

- **Padding** — Drag spots to increase or decrease padding visually.
- **Margin** — Visual margin controls around components.
- **Column Resizing** — Drag handles between columns to resize.
- **Toolbar** — Contextual component toolbar on selection.
- **Context Menus** — Right-click menus for quick actions.

![Canvas Spots](./screenshots/Screenshot%202026-04-13%20at%2012.46.14.png)

---

### Edit Collections Modal

When a collection component is added to the canvas, a modal lets you select which datasource collection it should repeat over — connecting your design to your data in one step.

<img src="./screenshots/Screenshot%202026-04-13%20at%2013.29.59.png" height="300" alt="Edit Collections" />

---

### Query Builder

When a condition component is added, a visual query builder lets you define the logic that controls its rendering. Build conditions across multiple fields and operators without writing any code.

![Query Builder 1](./screenshots/Screenshot%202026-04-13%20at%2013.30.46.png)

![Query Builder 1](./screenshots/Screenshot%202026-04-13%20at%2013.31.04.png)

![Query Builder 3](./screenshots/Screenshot%202026-04-13%20at%2013.31.31.png)

---

## Ready to Build?

grapesjs-shadcn gives you a production-ready visual editor with datasources, a full style system, Google Fonts, reusable symbols, and a polished shadcn UI — all in one package.

**[→ Get grapesjs-shadcn on GJS Market](https://gjs.market/products/grapesjs-shadcn)**

---

## Tech Stack

| Layer             | Technology  |
| ----------------- | ----------- |
| Build Tool        | Vite        |
| UI Framework      | React       |
| Component Library | shadcn/ui   |
| Page Builder Core | GrapesJS    |
| Rich Text Editor  | ProseMirror |

---

_Built with ❤️ using GrapesJS and shadcn/ui._

---

**[→ Purchase grapesjs-shadcn on GJS Market](https://gjs.market/products/grapesjs-shadcn)**
