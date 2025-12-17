# SVG Canvas Studio Pro 🎨

A professional, browser-based SVG design and animation tool with advanced features for creating, editing, and animating vector graphics. Built with React and Tailwind CSS as a single HTML file for easy deployment.

## ✨ Features

### 🎯 Core Editing
- **Multi-Selection**: Ctrl/Cmd+Click to select multiple objects
- **Transform Tools**: Scale, rotate, and move all element types including complex shapes
- **Path Editing**: Direct manipulation of Bezier curves and polygon points
- **Smart Grouping**: Group and ungroup elements with proper hierarchy
- **Layer Management**: Intuitive layers panel with visual hierarchy and drag-drop

### 🎨 Drawing & Shapes
- **20+ Built-in Shapes**: Rectangles, circles, polygons (triangle, pentagon, hexagon, octagon), stars, hearts, diamonds, arrows, lightning, clouds, and more
- **Custom Paths**: Draw and edit custom Bezier paths with control points
- **Text Tool**: Add and edit text with font customization
- **Line Tool**: Create lines with optional arrow markers

### 🌈 Styling
- **Solid & Gradient Fills**: Multi-stop gradients with unlimited color stops
- **Stroke Customization**: Width, dash patterns, and colors
- **Opacity Control**: Per-element transparency
- **Drop Shadows**: Optional shadow effects
- **Border Radius**: Rounded corners for rectangles

### 🎬 Advanced Animation System
- **20 Animation Presets**:
  - **Entrance**: Fade In, Slide (Up/Down/Left/Right), Zoom In, Rotate In, Pop In
  - **Attention**: Pulse, Float, Spin, Bounce, Rubber Band, Shake, Flip
  - **Special**: Custom Move, Morph, Draw Path
  - **Style**: Color Change (with gradient support), Text Size
  
- **Animation Controls**:
  - Drag-and-drop reordering of animation steps
  - Customizable duration, delay, and easing curves
  - Visual timeline with global sequence view
  - Auto-sequencer for instant sequential arrangement
  - Green target handles for custom move animations
  - Gradient color shifts with hue rotation and saturation

### 📥 Import & Export
- **SVG Import**: Load and edit existing SVG files with full element support
  - **Complete Element Support**: Paths, rectangles, circles, ellipses, polygons, polylines, lines, and text
  - **Transform Preservation**: Accurately parses translate, rotate, scale, and matrix transforms
  - **Nested Groups**: Maintains SVG group hierarchy with proper nesting
  - **Style Parsing**: Reads fill, stroke, opacity, and other attributes from both attributes and inline styles
  - **Fully Editable**: All imported elements become fully editable with resize, rotate, and style controls
- **Image Vectorization**: Convert PNG/JPG images to editable vector paths
- **Smart Grouping**: Imported SVGs automatically grouped for easy manipulation (ungroup to edit individual elements)
- **Clean Export**: Export to SVG with all animations and transforms preserved
- **Templates**: 8+ built-in SVG templates for quick starts

### 🎮 User Interface
- **Responsive Design**: Works on desktop and mobile devices
- **Purple Glass Theme**: Modern, professional dark UI
- **Grid & Snap**: Optional grid overlay for precision
- **Smart Guides**: Intelligent alignment guides with automatic snapping (see below)
- **Zoom & Pan**: Smooth viewport controls with mouse wheel
- **Keyboard Shortcuts**: Ctrl/Cmd for multi-select, Shift for proportional scaling
- **Touch Support**: Full touch screen compatibility

### 📏 Smart Guides (New!)
Intelligent positioning system that helps align objects precisely:
- **Auto-Detection**: Automatically detects when edges, centers, or corners align
- **Visual Feedback**: Green dashed lines appear when alignment is detected
- **Smart Snapping**: Objects snap to alignment points within 5px threshold
- **6 Alignment Types**: Left, right, center (horizontal), top, bottom, middle (vertical)
- **Toggle On/Off**: Click the alignment icon in the toolbar to enable/disable
- **Works While Dragging**: Real-time alignment detection as you move objects

## 🚀 Getting Started

### Quick Start
1. **Add Shapes**: Click the shape menu (☰) in the toolbar to add any shape
2. **Select & Edit**: Click to select, drag handles to resize/rotate
3. **Style**: Use the Properties panel to change colors, gradients, and strokes
4. **Animate**: Switch to Timeline tab, click + to add animations, drag to reorder
5. **Export**: Click download icon to save your animated SVG

### Transform Controls
- **Resize**: Drag corner handles (hold Shift for proportional)
- **Rotate**: Drag the top-center circular handle
- **Move**: Drag the object directly
- **Edit Points**: Click Edit Points button for paths/polygons

### Animation Workflow
1. Select an element
2. Switch to Properties or Timeline tab
3. Click **+** to add an animation
4. Choose animation type from dropdown
5. Adjust duration, delay, and easing
6. Drag the menu icon (☰) to reorder steps
7. Press Play to preview
8. Export to save with animations

## 🎓 Tips & Tricks

### Color Animations
- **Solid Fills**: Set target color for smooth transitions
- **Gradients**: Use Hue Rotate and Saturate controls for dynamic color shifts

### Custom Move Animations
- Add a "Custom Move" animation
- Drag the green numbered target on canvas to set destination
- Element will smoothly animate to that position

### Path Drawing Animation
- Works best on shapes with strokes
- Creates drawing/writing effect
- Automatically calculates stroke length

### Multi-Selection
- Ctrl/Cmd+Click to add elements to selection
- Group button creates a group from selected items
- Ungroup button releases children from a group

### Layer Management
- Layers panel shows all objects in reverse render order (top = front)
- Click layer to select, Ctrl/Cmd+Click for multi-select
- Groups show expandable children when selected
- Visual indicators for locked (🔒) and animated (▶) objects

## 🛠️ Technical Details

### Technology Stack
- **React 18**: Component-based UI
- **Tailwind CSS**: Utility-first styling
- **Lucide Icons**: Beautiful SVG icons
- **ImageTracerJS**: Bitmap to vector conversion
- **Pure SVG**: No canvas, all native SVG rendering

### Architecture
- Single HTML file (~2000 lines)
- No build process required
- Client-side only (no server needed)
- Uses native browser APIs (DOMParser, XMLSerializer)

### Transform System
- `getBoundingBox()`: Calculates proper bounds for all shape types
- Rotation transforms applied at shape centers
- Scale operations preserve shape structure
- Polygon/path coordinates scaled proportionally

### Animation Export
- Keyframes generated for all animation types
- Elements tagged with `data-element-id` for reliable matching
- Initial states (opacity, transforms) applied correctly
- CSS animations compatible with all modern browsers

## 📋 Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| Ctrl/Cmd + Click | Multi-select elements |
| Shift + Drag | Proportional resize |
| Mouse Wheel | Zoom in/out |
| Ctrl/Cmd + D | Duplicate (via duplicate button) |
| Delete | Remove selected (via trash button) |
| Double Click | Edit text content |

## 🎨 Animation Presets Reference

### Entrance Animations
Start with element hidden, animate to visible state:
- `fadeIn`: Opacity 0 → 1
- `slideUp/Down/Left/Right`: Move + fade from direction
- `zoomIn`: Scale from 0.3
- `rotateIn`: Rotate from -180°
- `scale`: Pop from scale 0

### Attention Animations
Continuous or repeating effects:
- `pulse`: Subtle scale bounce
- `float`: Vertical oscillation
- `spin`: Continuous rotation
- `bounce`: Physics-based bounce
- `rubberBand`: Elastic stretch
- `shake`: Horizontal vibration
- `flip`: 360° Y-axis rotation

### Special Animations
- `move`: Custom path movement (drag green target)
- `morph`: Scale + rotate bounce effect
- `draw`: Stroke drawing animation

### Style Animations
- `color`: Smooth color transitions (gradients use hue-rotate)
- `textSize`: Font size scaling

## 🐛 Known Limitations

- Very complex SVG imports may lose some styling
- Animations on nested groups may have transform conflicts
- Gradient animations use filters (not full color control)
- Export size limited by browser memory

## 📝 License

This project is licensed under the **PolyForm Noncommercial License 1.0.0**. 

### ✅ What you CAN do:
- **Personal Use**: Use the software for hobby projects, private entertainment, or personal study.
- **Research & Education**: Use it for research, experiments, or in educational institutions.
- **Modify & Share**: Make changes to the code and share it with others (as long as they get this same license).

### ❌ What you CANNOT do:
- **Commercial Use**: Use the software for any purpose intended for commercial advantage or monetary compensation is strictly forbidden.
- **Sell the Software**: You cannot sell the software or services based on it.
- **Business Use**: Use it within a for-profit company for business operations.

See the [LICENSE](LICENSE) file for the full legal text.

## 🤝 Contributing

This is a single-file project for maximum portability. To contribute:
1. Edit `index.html`
2. Test in multiple browsers
3. Ensure no external dependencies added
4. Maintain the single-file architecture
