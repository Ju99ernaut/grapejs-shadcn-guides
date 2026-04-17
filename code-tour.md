# GrapesJS + shadcn/ui: Getting Started with grapesjs-shadcn

> Get started with grapesjs-shadcn and explore the key files used to configure the editor, layout, UI, and extensibility points.

**[→ Get grapesjs-shadcn on GJS Market](https://gjs.market/products/grapesjs-shadcn)**

---

## Introduction

grapesjs-shadcn is a modern GrapesJS preset built with React, `@grapesjs/react`, shadcn/ui, and Tailwind CSS. It gives you a polished editor foundation that is easy to run, easy to extend, and structured so you can customize the experience without fighting the default GrapesJS UI.

It is designed for teams building page builders, email builders, document builders, and data-driven template editors.

This post gives a practical overview of how to get up and running, plus a project tour showing where to configure the major parts of the editor.

---

## Getting Started

To run the project locally:

```bash
cd grapesjs-shadcn
pnpm i
pnpm run dev
```

That is enough to get the editor running locally so you can start exploring the structure and modifying it for your own use case.

---

## Project Tour

The project is organized so the main editor layout, configuration, and UI pieces are easy to find and replace.

### `src/App.tsx`

Start here.

This is where the app mounts the editor and wraps it with the providers used by the default setup, including `ThemeProvider` and `GoogleFontsProvider`. It is also where the main `GrapesJsEditor` layout is added.

In practice, this file is the entry point for the editor experience. If you want to change the surrounding app-level providers, global editor wrappers, or how the editor is mounted into the app, this is the first place to look.

---

### `src/layouts/editor/index.tsx`

This is the main editor layout.

It contains the structure of the editor UI, the composition of the panels and layout regions, and the GrapesJS configuration used by the editor. This is one of the most important files in the project because it is where you can adapt the editor to your own product needs. For example, this is where you may:

- add GrapesJS plugins
- change enabled modules
- swap default panels
- wire in your own custom UI
- adjust how the layout is composed

Around this file, you will also find the components that support the default provided editor layout.

---

### `src/layouts/editor/config`

This folder breaks out parts of the GrapesJS configuration into focused files — for example, `src/layouts/editor/config/style-manager`.

This structure keeps the main editor layout cleaner and makes it easier to customize one subsystem at a time. Instead of keeping all configuration in a single large file, editor concerns can be split into smaller, more maintainable pieces. A good pattern is to keep feature-specific config here whenever the setup grows beyond basic defaults.

---

## Blocks Manager

The blocks manager is where users discover and drag content into the canvas.

The default UI is built to feel cleaner and more scalable than the stock GrapesJS panel, with support for search and grouping. When customizing it, you will typically focus on block registration, group organization, search and filter behavior, and how blocks are rendered in the panel.

If you want to expand the builder for pages, emails, or documents, this is usually one of the first systems you will extend.

---

## Layers Manager

The layers manager gives users a clear tree view of the components on the canvas.

The default implementation provides a cleaner hierarchy and editing experience while staying close to GrapesJS concepts. It is useful when you want to improve selection clarity, customize layer rendering, add richer labels or icons, or make deeply nested content easier to navigate.

### Component Icons

For component icons, look at `src/components/grapesjs/layer-manager/icon.tsx`. This is where icons can be mapped to component types and block IDs. That mapping can be reused across block icons, layer icons, and badge icons — giving you a single place to define a more expressive visual system for your editor components.

---

## Project Manager

The project manager is linked to the storage manager.

It is designed to work well with persisted editor state, and can be extended by building a storage layer with a structure similar to `src/components/grapesjs/project-manager/storage.ts`. That makes it a useful starting point if you want to support project save/load flows, renaming, duplication, custom persistence logic, or remote and local project storage.

If you are integrating with your own backend, the storage manager and project manager usually evolve together.

---

## Pages Manager

The pages manager supports multi-page workflows and is useful for builders that need more than a single canvas page.

Typical use cases include documents with multiple pages, landing page flows, email variants, and structured template systems. The default setup is intended to be easy to adapt if your product needs page creation, switching, duplication, or renaming.

---

## Theme Manager

The theme manager lets you configure reusable theme values for the editor UI and editing experience.

Its config lives at `src/components/grapesjs/theme-manager/consts.tsx`. This is a good place to define and evolve the values used for theming and styling choices in the default theme manager UI.

---

## Asset Manager

The asset manager is configured through the editor config. This is where you would control behavior such as uploads, asset sources, modal behavior, insertion flows, and drag-and-drop asset usage.

Because it is wired through editor configuration, it is straightforward to replace the default behavior with your own backend or media pipeline.

---

## Top Bar

The top bar is where common commands and controls are exposed.

To customize it, check `src/layouts/editor/top-bar.tsx`. This is the place to add commands, buttons, toggles, editor controls, and workflow shortcuts. If you want to expose more editor actions in the default UI, this is the main entry point.

---

## Selector Manager

The selector manager handles classes and style targeting.

This is useful when you want users to add or remove classes, work with reusable styling, target component states, or build a more design-system-oriented editing workflow. It complements the style manager and helps bridge visual editing with more structured CSS management.

---

## Trait Manager

The trait manager is configured per component and supports categories, making it easier to organize component settings into clearer groups instead of showing everything in one flat list.

### Category Icons

Category icons are defined at `src/components/grapesjs/traits-manager/consts.tsx`. This gives you a centralized place to control how trait categories are represented visually in the UI.

---

## Style Manager

The style manager configuration is broken out into the editor config folder at `src/layouts/editor/config/style-manager`.

This makes it easier to customize sectors, properties, inputs, and the overall styling experience without cluttering the main editor layout. It is a good place to tailor the editor for your own design system, especially if you want more opinionated controls for spacing, typography, layout, or component-specific styling.

---

## Symbols

Symbols provide reusable components that can share structure or styling across instances.

They are useful for patterns like repeated sections, reusable headers and footers, shared content blocks, and synchronized design elements. If your editor needs stronger reuse primitives, symbols are one of the most valuable systems to build around.

---

## Google Fonts Integration

Google Fonts support is provided through the app-level provider setup. The editor is wrapped with `GoogleFontsProvider` in `src/App.tsx`.

This keeps font loading and font-related UI concerns separated from the core editor layout while still making them easy to integrate into styling controls and text editing workflows.

---

## Canvas Spots

Canvas spots provide direct visual controls on the canvas itself. You can explore them in `src/components/grapesjs/canvas-spots`.

This is where the UI around on-canvas editing affordances lives, including interactions like spacing adjustments, visual handles, and contextual overlays. Canvas spots are especially useful when you want more direct manipulation and less panel-driven editing.

---

## Rich Text Editor

The default rich text editor uses the open-source `grapesjs-prosemirror` plugin. Custom UI for the RTE lives in `src/components/grapesjs/rte`.

This setup gives you a stronger base than the default text editing experience and makes it easier to build richer formatting tools with a custom interface. If text editing is a major part of your builder, this is one of the most important areas to explore.

---

## Datasources & Dynamic Content

Datasources and dynamic content are built as UI around the GrapesJS API.

This part of the project is especially useful for advanced builder workflows where components need to bind to data, support variables, or participate in runtime-driven content generation. Because the UI is built around GrapesJS rather than hidden inside it, it is easier to evolve this area into something more specialized for your own application — whether that means variables, schema-driven content, collections, dynamic rendering, or conditional logic.

---

## Framework Flexibility

The development setup uses Vite, but the UI pieces are plain React components. That makes the project flexible if you want to reuse the editor UI in other React environments, including Next.js.

The overall structure is meant to be portable, so you can use the default layout as-is or gradually replace parts of it with your own product-specific implementation.

---

## Closing Thoughts

The goal of grapesjs-shadcn is not just to make GrapesJS look better. It is to provide a cleaner starting point for teams building serious visual editors with React.

The fastest way to understand it is to run the project, start in `src/App.tsx`, move to `src/layouts/editor/index.tsx`, then explore the feature-specific folders and config files. From there, you can decide which parts to keep, which parts to rework, and how deeply you want to tailor the editor for your own builder workflow.

---

**[→ Get grapesjs-shadcn on GJS Market](https://gjs.market/products/grapesjs-shadcn)**
