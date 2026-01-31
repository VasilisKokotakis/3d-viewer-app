# 3D Model Viewer MVP

A simple, clean 3D model viewer built with React and Three.js for displaying GLTF models.

## 🚀 Features

- ✅ Load and display GLTF/GLB models
- ✅ Orbit controls (rotate, zoom, pan)
- ✅ Auto-scaling and centering of models
- ✅ Professional lighting setup
- ✅ Responsive design
- ✅ Loading states and error handling

## 📦 Installation

```bash
# Install dependencies
npm install

# Start development server
npm run dev

# Build for production
npm run build
```

## 📁 Project Structure

```
3d-viewer-app/
├── public/
│   └── models/              # Put your GLTF files here
│       ├── your-model.gltf
│       ├── textures/
│       └── *.bin
├── src/
│   ├── components/
│   │   ├── ModelViewer.jsx  # Main 3D canvas component
│   │   └── Model.jsx        # GLTF loader component
│   ├── App.jsx              # Main app
│   ├── App.css
│   ├── main.jsx
│   └── index.css
├── package.json
└── vite.config.js
```

## 🎯 How to Use

### 1. Add Your 3D Models

Create a `public/models/` folder and place your GLTF files there:

```
public/
└── models/
    ├── robot.gltf
    ├── robot.bin
    └── textures/
        └── robot_texture.png
```

### 2. Update the Model Path

In `src/App.jsx`, change the model path:

```javascript
const [modelPath, setModelPath] = useState('/models/robot.gltf')
```

### 3. Run the App

```bash
npm run dev
```

Your browser will open at `http://localhost:3000`

## 🎮 Controls

- **Left Click + Drag**: Rotate the model
- **Right Click + Drag**: Pan the camera
- **Scroll Wheel**: Zoom in/out

## 🔧 Customization

### Change Camera Position

In `ModelViewer.jsx`:

```javascript
<PerspectiveCamera makeDefault position={[0, 0, 5]} fov={50} />
```

### Adjust Lighting

In `ModelViewer.jsx`:

```javascript
<ambientLight intensity={0.5} />
<directionalLight position={[10, 10, 5]} intensity={1} />
```

### Enable Auto-Rotation

In `Model.jsx`, uncomment:

```javascript
useFrame(() => {
  if (groupRef.current) {
    groupRef.current.rotation.y += 0.001
  }
})
```

### Change Background

In `ModelViewer.jsx`, modify the Environment preset:

```javascript
<Environment preset="sunset" /> // Options: sunset, dawn, night, warehouse, forest, apartment, studio, city, park, lobby
```

## 📚 Tech Stack

- **React 18** - UI framework
- **Three.js** - 3D rendering engine
- **@react-three/fiber** - React renderer for Three.js
- **@react-three/drei** - Useful helpers for React Three Fiber
- **Vite** - Fast build tool and dev server

## 🐛 Troubleshooting

### Model doesn't load

1. Check the file path is correct
2. Ensure all files (.gltf, .bin, textures) are in `/public/models/`
3. Check browser console for errors
4. Verify the GLTF file is valid (use https://gltf-viewer.donmccurdy.com/)

### Model appears too small/large

The auto-scaling should handle this, but you can manually adjust in `Model.jsx`:

```javascript
const scale = 2 / maxDim // Change the 2 to make bigger/smaller
```

### Performance issues

1. Reduce model complexity
2. Optimize textures (use smaller sizes)
3. Use GLB format instead of GLTF (single file, faster to load)

## 🎨 Example Models

You can test with free models from:
- [Sketchfab](https://sketchfab.com/features/gltf) (download as GLTF)
- [Three.js Examples](https://github.com/mrdoob/three.js/tree/dev/examples/models/gltf)
- [Poly Haven](https://polyhaven.com/models)

## 📝 Next Steps (Beyond MVP)

- Multiple model selection
- File upload functionality
- Screenshot/export features
- Annotation tools
- Material/texture editing
- Animation playback
- VR support

## 📄 License

MIT - Feel free to use this for your projects!

---

Built with ❤️ using React and Three.js
# 3D-Viewer
# test
