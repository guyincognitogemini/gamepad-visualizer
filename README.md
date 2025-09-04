# 🎮 Gamepad Visualizer  

## Project Charter  

### Goal  
To build a **web-based Xbox 360 controller visualizer** that runs entirely in the browser, powered by the [Gamepad API]. The tool will:  

- **Detect and display** an Xbox 360 (XInput) gamepad layout.  
- **Render the controller** using a provided **spritesheet (`style-g-large.png`) and XML atlas**.  
- **Map all controls** (ABXY, D-Pad, Sticks, Shoulder Buttons, Triggers, Start/Select) to their proper positions.  
- **Provide visual feedback** to live input (pressed buttons highlight, stick nubs move, triggers animate).  

### Why  
- A **stable baseline** for controller visualization that can be easily expanded.  
- A **developer/debug tool** for verifying controller input and mappings.  
- A **reference implementation** for working with PixiJS + Gamepad API + sprite atlases.  
- A **publicly hosted demo** (via GitHub Pages) that’s always up-to-date and can be shared easily.  

### Workflow  
- **Core stack**: Vite (scaffold + build), PixiJS (rendering), Gamepad API (input).  
- **Assets**: Use `style-g-large.png` with atlas definitions + alias mappings.  
- **Deployment**: `npm run deploy` → GitHub Pages for live updates.  
- **Iteration**: Maintain a stable `main` branch, add new features via PRs/branches, and evolve the visualizer incrementally.  

---

## 🚀 Setup  

### Requirements  
- Node.js (>= 18)  
- npm (>= 9)  

### Scaffold  
```bash
# Create project folder
mkdir gamepad-visualizer
cd gamepad-visualizer

# Initialize Vite project
npm create vite@latest . -- --template vanilla

# Install dependencies
npm install pixi.js
npm install gh-pages --save-dev
```

### Configure `package.json`  
```json
"scripts": {
  "dev": "vite",
  "build": "vite build",
  "preview": "vite preview",
  "predeploy": "npm run build",
  "deploy": "gh-pages -d dist"
}
```

---

## 📂 Project Structure  

```
gamepad-visualizer/
 ├─ public/
 │   └─ assets/
 │        ├─ style-g-large.png
 │        └─ atlas.xml
 ├─ index.html
 ├─ main.js
 ├─ package.json
```

---

## 🕹 Usage  

### Local Dev  
```bash
npm run dev
```
- Opens at `http://localhost:5173`  
- Connect your Xbox 360 controller → layout appears, inputs highlight.  

### Build  
```bash
npm run build
```
- Bundles project into `/dist`.  

### Deploy  
```bash
npm run deploy
```
- Publishes `/dist` to GitHub Pages (`gh-pages` branch).  

---

## ✨ Future Features  
- Visual themes (different skins from the atlas).  
- Multi-controller support.  
- Button labels (A/B/X/Y text).  
- Input history overlay.  
- Recording + playback of input sequences.  

---

## 📜 License & Credits  

The controller spritesheet and atlas are from **Kenney’s “Mobile Controls (1.0)” pack**.  

- **Author**: [Kenney](https://www.kenney.nl)  
- **License**: [Creative Commons Zero, CC0](http://creativecommons.org/publicdomain/zero/1.0/)  
  - Free to use for personal, educational, and commercial purposes.  
  - Credit to “Kenney” or [www.kenney.nl](https://www.kenney.nl) is appreciated but not required.  

If you find this project useful, consider [donating to Kenney](https://www.kenney.nl/donate) or supporting via [Patreon](https://patreon.com/kenney).  
