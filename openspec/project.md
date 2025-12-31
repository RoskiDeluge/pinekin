# Project Context

## Purpose
Pinekin is a browser-based game prototype built with PixiJS and Spine animations. The current goal is a playable scene with a controllable character, parallax environment, and simple movement/animation states.

## Tech Stack
- JavaScript (ES modules)
- PixiJS v8 (rendering)
- spine-pixi-v8 (Spine animation runtime)
- Parcel (dev server and bundler)
- Babel (transpilation as needed)

## Project Conventions

### Code Style
- ES module imports/exports, class-based modules per file
- CamelCase for classes (e.g., `SpineBoy`, `Controller`), lowerCamelCase for variables
- Prefer small, focused classes (input, scene, character)
- Inline comments only where logic is non-obvious

### Architecture Patterns
- Simple scene graph: `Scene` owns environment layers, `SpineBoy` owns character animations
- `Controller` captures keyboard input and exposes state to the game loop
- Single update loop driven by `app.ticker` in `src/index.js`

### Testing Strategy
- No automated tests yet; manual validation in browser is the current approach

### Git Workflow
- Not defined yet (suggest: feature branches + descriptive commits)

## Domain Context
- Game input: WASD/arrow keys for movement, Space for jump
- Movement state drives animation selection; scene scrolls based on character direction and speed
- Assets are currently loaded from external URLs (PixiJS/Spine demo assets)

## Important Constraints
- Browser-only runtime; keep dependencies lightweight
- Must run via `index.html` or `parcel` without server-side components

## External Dependencies
- PixiJS assets and Spine demo files hosted on `pixijs.com` and GitHub raw URLs
