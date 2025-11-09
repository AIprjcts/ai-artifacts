# Image to Excalidraw Converter Skill

## Overview
This skill enables Claude to analyze images and convert them into Excalidraw-compatible JSON format. The conversion preserves visual elements, spatial relationships, and styling while mapping to Excalidraw's native elements or custom SVG components.

## Core Capabilities
- ✅ Analyze images using Claude's vision API
- ✅ Identify shapes, text, colors, layouts, and complex elements
- ✅ Map to Excalidraw native elements (rectangle, ellipse, diamond, arrow, line, text, image)
- ✅ Generate custom SVG for complex shapes, icons, and logos
- ✅ Preserve spatial relationships and proportions
- ✅ Extract and format text with appropriate styling
- ✅ Handle colors, strokes, fills, and opacity
- ✅ Create grouped elements and relationships

## Excalidraw JSON Format Specification

### File Structure
```json
{
  "type": "excalidraw",
  "version": 2,
  "source": "https://excalidraw.com",
  "elements": [],
  "appState": {
    "gridSize": null,
    "viewBackgroundColor": "#ffffff"
  },
  "files": {}
}
```

### Element Types

#### 1. Rectangle
```json
{
  "id": "unique-id",
  "type": "rectangle",
  "x": 100,
  "y": 100,
  "width": 200,
  "height": 100,
  "angle": 0,
  "strokeColor": "#1e1e1e",
  "backgroundColor": "#transparent",
  "fillStyle": "solid",
  "strokeWidth": 2,
  "strokeStyle": "solid",
  "roughness": 1,
  "opacity": 100,
  "groupIds": [],
  "frameId": null,
  "roundness": { "type": 3, "value": 8 },
  "seed": 1234567890,
  "version": 1,
  "versionNonce": 123456789,
  "isDeleted": false,
  "boundElements": null,
  "updated": 1699999999999,
  "link": null,
  "locked": false
}
```

#### 2. Ellipse
```json
{
  "id": "unique-id",
  "type": "ellipse",
  "x": 100,
  "y": 100,
  "width": 150,
  "height": 150,
  "angle": 0,
  "strokeColor": "#1e1e1e",
  "backgroundColor": "transparent",
  "fillStyle": "solid",
  "strokeWidth": 2,
  "strokeStyle": "solid",
  "roughness": 1,
  "opacity": 100,
  "groupIds": [],
  "frameId": null,
  "roundness": null,
  "seed": 1234567890,
  "version": 1,
  "versionNonce": 123456789,
  "isDeleted": false,
  "boundElements": null,
  "updated": 1699999999999,
  "link": null,
  "locked": false
}
```

#### 3. Diamond
```json
{
  "id": "unique-id",
  "type": "diamond",
  "x": 100,
  "y": 100,
  "width": 150,
  "height": 150,
  "angle": 0,
  "strokeColor": "#1e1e1e",
  "backgroundColor": "transparent",
  "fillStyle": "solid",
  "strokeWidth": 2,
  "strokeStyle": "solid",
  "roughness": 1,
  "opacity": 100,
  "groupIds": [],
  "frameId": null,
  "roundness": { "type": 2 },
  "seed": 1234567890,
  "version": 1,
  "versionNonce": 123456789,
  "isDeleted": false,
  "boundElements": null,
  "updated": 1699999999999,
  "link": null,
  "locked": false
}
```

#### 4. Arrow
```json
{
  "id": "unique-id",
  "type": "arrow",
  "x": 100,
  "y": 100,
  "width": 200,
  "height": 0,
  "angle": 0,
  "strokeColor": "#1e1e1e",
  "backgroundColor": "transparent",
  "fillStyle": "solid",
  "strokeWidth": 2,
  "strokeStyle": "solid",
  "roughness": 1,
  "opacity": 100,
  "groupIds": [],
  "frameId": null,
  "roundness": { "type": 2 },
  "seed": 1234567890,
  "version": 1,
  "versionNonce": 123456789,
  "isDeleted": false,
  "points": [[0, 0], [200, 0]],
  "lastCommittedPoint": null,
  "startBinding": null,
  "endBinding": null,
  "startArrowhead": null,
  "endArrowhead": "arrow",
  "updated": 1699999999999,
  "link": null,
  "locked": false
}
```

#### 5. Line
```json
{
  "id": "unique-id",
  "type": "line",
  "x": 100,
  "y": 100,
  "width": 150,
  "height": 150,
  "angle": 0,
  "strokeColor": "#1e1e1e",
  "backgroundColor": "transparent",
  "fillStyle": "solid",
  "strokeWidth": 2,
  "strokeStyle": "solid",
  "roughness": 1,
  "opacity": 100,
  "groupIds": [],
  "frameId": null,
  "roundness": { "type": 2 },
  "seed": 1234567890,
  "version": 1,
  "versionNonce": 123456789,
  "isDeleted": false,
  "points": [[0, 0], [50, 50], [150, 150]],
  "lastCommittedPoint": null,
  "startBinding": null,
  "endBinding": null,
  "startArrowhead": null,
  "endArrowhead": null,
  "updated": 1699999999999,
  "link": null,
  "locked": false
}
```

#### 6. Text
```json
{
  "id": "unique-id",
  "type": "text",
  "x": 100,
  "y": 100,
  "width": 200,
  "height": 25,
  "angle": 0,
  "strokeColor": "#1e1e1e",
  "backgroundColor": "transparent",
  "fillStyle": "solid",
  "strokeWidth": 2,
  "strokeStyle": "solid",
  "roughness": 0,
  "opacity": 100,
  "groupIds": [],
  "frameId": null,
  "roundness": null,
  "seed": 1234567890,
  "version": 1,
  "versionNonce": 123456789,
  "isDeleted": false,
  "boundElements": null,
  "updated": 1699999999999,
  "link": null,
  "locked": false,
  "text": "Sample Text",
  "fontSize": 20,
  "fontFamily": 1,
  "textAlign": "left",
  "verticalAlign": "top",
  "baseline": 18,
  "containerId": null,
  "originalText": "Sample Text",
  "lineHeight": 1.25
}
```

#### 7. Image
```json
{
  "id": "unique-id",
  "type": "image",
  "x": 100,
  "y": 100,
  "width": 300,
  "height": 200,
  "angle": 0,
  "strokeColor": "transparent",
  "backgroundColor": "transparent",
  "fillStyle": "solid",
  "strokeWidth": 1,
  "strokeStyle": "solid",
  "roughness": 0,
  "opacity": 100,
  "groupIds": [],
  "frameId": null,
  "roundness": null,
  "seed": 1234567890,
  "version": 1,
  "versionNonce": 123456789,
  "isDeleted": false,
  "boundElements": null,
  "updated": 1699999999999,
  "link": null,
  "locked": false,
  "status": "saved",
  "fileId": "file-id-reference",
  "scale": [1, 1]
}
```

### Files Object (for images/SVGs)
```json
{
  "files": {
    "file-id-reference": {
      "mimeType": "image/svg+xml",
      "id": "file-id-reference",
      "dataURL": "data:image/svg+xml;base64,BASE64_ENCODED_SVG",
      "created": 1699999999999,
      "lastRetrieved": 1699999999999
    }
  }
}
```

## Image Analysis Guidelines

### Step 1: Initial Analysis
When an image is uploaded, analyze:
1. **Overall layout**: Grid structure, alignment, spacing
2. **Shape types**: Circles, rectangles, triangles, lines, curves
3. **Text content**: Labels, titles, annotations, fonts
4. **Colors**: Stroke colors, fill colors, gradients
5. **Relationships**: Connections between elements, groupings
6. **Complexity**: Simple shapes vs. complex icons/logos

### Step 2: Element Classification
Classify each visual element as:

#### Simple Shapes (map to Excalidraw native)
- Rectangles/squares → `rectangle`
- Circles/ovals → `ellipse`
- Diamond shapes → `diamond`
- Straight lines → `line`
- Arrows/connectors → `arrow`
- Text → `text`

#### Complex Shapes (generate SVG)
- Logos
- Icons with multiple paths
- Custom shapes with curves
- Gradients
- Complex patterns
- Images/photos

### Step 3: Spatial Mapping
- Determine canvas size (default: 1000x800 or match image aspect ratio)
- Calculate relative positions maintaining proportions
- Preserve alignment and spacing
- Group related elements

## Shape Mapping Rules

### Rectangle Mapping
- Detect: Sharp corners, 4 sides, right angles
- Round corners: Use `roundness: { type: 3, value: 8-32 }`
- Properties: width, height, stroke, fill

### Ellipse Mapping
- Detect: Circular or oval shapes
- Perfect circles: width === height
- Properties: width, height (as diameter)

### Diamond Mapping
- Detect: Rotated squares or diamond orientations
- Use for: Decision points, special markers
- Properties: width, height, rotation angle

### Arrow Mapping
- Detect: Lines with directional indicators
- Types: straight arrows, curved arrows
- Points: Calculate path coordinates
- Arrowheads: `startArrowhead`, `endArrowhead` can be "arrow", "bar", "dot", or null

### Line Mapping
- Detect: Straight or multi-segment lines
- Use points array for polylines
- Properties: strokeWidth, strokeStyle

### Text Mapping
- Extract text content using OCR/vision
- Detect: font size (approximate to 16, 20, 28, 36)
- Font families: 1=Virgil (hand-drawn), 2=Helvetica, 3=Cascadia
- Alignment: "left", "center", "right"
- Calculate approximate width/height based on text length

## Color Mapping

### Standard Excalidraw Colors
- Black: `#1e1e1e`
- Dark Gray: `#343a40`
- Gray: `#495057`
- Light Gray: `#c92a2a`
- Red: `#c92a2a`
- Pink: `#a61e4d`
- Grape: `#862e9c`
- Violet: `#5f3dc4`
- Indigo: `#364fc7`
- Blue: `#1864ab`
- Cyan: `#0b7285`
- Teal: `#087f5b`
- Green: `#2b8a3e`
- Lime: `#5c940d`
- Yellow: `#e67700`
- Orange: `#d9480f`

### Color Detection
- Map detected colors to closest Excalidraw palette color
- Use "transparent" for no fill
- Preserve opacity (0-100)

## Style Properties

### Fill Styles
- `"solid"`: Solid fill
- `"hachure"`: Hand-drawn hatching
- `"cross-hatch"`: Cross-hatched fill

### Stroke Styles
- `"solid"`: Solid line
- `"dashed"`: Dashed line
- `"dotted"`: Dotted line

### Roughness
- `0`: Architect mode (precise, clean lines)
- `1`: Artist mode (hand-drawn, default)
- `2`: Cartoonist mode (very rough)

## SVG Generation for Complex Elements

### When to Generate SVG
Generate custom SVG for:
- Logos and brand icons
- Complex multi-path shapes
- Icons from icon libraries (FontAwesome, Material, etc.)
- Curved paths that can't be represented with native elements
- Gradients and advanced styling

### SVG Format
```xml
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100">
  <path d="M10 10 L90 10 L50 90 Z" fill="#1e1e1e" stroke="#000" stroke-width="2"/>
</svg>
```

### Embedding SVG in Excalidraw
1. Generate clean, valid SVG markup
2. Base64 encode: `btoa(svgString)`
3. Create dataURL: `data:image/svg+xml;base64,${base64}`
4. Add to files object with unique ID
5. Create image element referencing the file ID

### SVG Best Practices
- Use viewBox for proper scaling
- Simplify paths when possible
- Use Excalidraw color palette
- Keep file size reasonable
- Test rendering in Excalidraw

## Grouping and Relationships

### Grouping Elements
Elements that form a logical unit should share a `groupIds` array:
```json
{
  "groupIds": ["group-123"]
}
```

### Binding Elements
Arrows can bind to shapes using `startBinding` and `endBinding`:
```json
{
  "startBinding": {
    "elementId": "shape-id",
    "focus": 0,
    "gap": 8
  }
}
```

### Text Containers
Text can be bound to shapes using `containerId`:
```json
{
  "type": "text",
  "containerId": "rectangle-id",
  "verticalAlign": "middle",
  "textAlign": "center"
}
```

## ID Generation

Generate unique IDs for each element:
```javascript
function generateId() {
  return Math.random().toString(36).substring(2, 15) +
         Math.random().toString(36).substring(2, 15);
}
```

Use consistent timestamp for `created` and `updated` fields.

## Conversion Workflow

### Phase 1: Analysis
1. Describe what you see in the image
2. Identify all distinct elements
3. Note spatial relationships and layout
4. Detect text content
5. Identify colors and styles

### Phase 2: Planning
1. Categorize elements (native vs. SVG)
2. Determine canvas size
3. Calculate coordinate mapping
4. Plan groupings
5. Identify connections

### Phase 3: Generation
1. Generate unique IDs
2. Create element JSON for each component
3. Generate SVG for complex elements
4. Set proper coordinates and dimensions
5. Apply colors and styles
6. Create groups and bindings

### Phase 4: Assembly
1. Combine all elements into elements array
2. Add files object for SVG/images
3. Set appState (viewBackgroundColor, etc.)
4. Validate JSON structure
5. Format for readability

### Phase 5: Output
1. Present the complete JSON
2. Offer download as .excalidraw file
3. Provide conversion summary
4. Suggest manual adjustments if needed
5. Show preview if React tool is available

## Example Conversions

### Example 1: Simple Flowchart
**Input**: Image with rectangles, arrows, and text
**Output**:
- Rectangles → rectangle elements
- Arrows → arrow elements with bindings
- Text → text elements (some as containers)
- Group all elements logically

### Example 2: Logo/Icon
**Input**: Complex logo with curves
**Output**:
- Generate SVG from visual description
- Create image element
- Add to files object
- Position appropriately

### Example 3: Diagram with Mixed Elements
**Input**: Shapes, icons, connectors, labels
**Output**:
- Simple shapes → native elements
- Icons → SVG images
- Connectors → arrows with bindings
- Labels → text elements

## Edge Cases and Best Practices

### Handling Ambiguity
- If shape type is unclear, prefer simpler native element
- Use SVG only when necessary
- Ask user for clarification on complex elements

### Quality Checks
- ✅ All IDs are unique
- ✅ Coordinates are reasonable (not negative or too large)
- ✅ Colors use valid hex codes or "transparent"
- ✅ Text width/height accommodates content
- ✅ Arrows connect to valid element IDs
- ✅ JSON is valid and properly formatted

### Performance Considerations
- Limit SVG complexity for better rendering
- Use native elements when possible
- Avoid excessive element count (>200 elements)
- Optimize coordinate precision (round to integers)

### User Interaction
- Always describe what you're converting
- Explain any simplifications made
- Offer alternatives for complex elements
- Provide instructions for manual refinement
- Generate downloadable files

## Output Format

### Standard Response Template
```
# Image to Excalidraw Conversion

## Analysis
[Describe what you see in the image]

## Conversion Plan
- Element count: X
- Native elements: Y
- Custom SVG elements: Z
- Canvas size: WxH

## Elements Detected
1. [Element 1 description] → [Excalidraw type]
2. [Element 2 description] → [Excalidraw type]
...

## Generated Excalidraw JSON

[Include complete JSON]

## Download
Save the above JSON as `filename.excalidraw` and open in Excalidraw.

## Notes
- [Any caveats or suggestions]
- [Recommended manual adjustments]
```

## Testing and Validation

### Before Outputting
1. Validate JSON syntax
2. Check all required properties are present
3. Verify coordinates are within reasonable bounds
4. Ensure colors are valid
5. Test that IDs are unique

### After Output
1. Recommend testing in Excalidraw
2. Offer to make adjustments
3. Provide troubleshooting tips

## Common Pitfalls to Avoid

❌ Missing required properties (version, seed, etc.)
❌ Invalid color formats
❌ Negative coordinates
❌ Zero or negative dimensions
❌ Duplicate IDs
❌ Invalid JSON syntax
❌ Missing commas or brackets
❌ Incorrect element types
❌ Mismatched binding IDs
❌ Invalid base64 encoding for images

## Advanced Features

### Libraries Integration
Reference Excalidraw libraries for common elements:
- Icons
- UI components
- Diagrams
- Shapes

### Custom Fonts
Font family options:
- 1: Virgil (default, hand-drawn)
- 2: Helvetica (clean, professional)
- 3: Cascadia (monospace, code)

### Frames
Group elements into frames for organization:
```json
{
  "type": "frame",
  "name": "Frame 1",
  "x": 0,
  "y": 0,
  "width": 500,
  "height": 400
}
```

## Continuous Improvement

Learn from each conversion:
- Note which mappings work well
- Identify common patterns
- Refine SVG generation
- Improve coordinate accuracy
- Enhance text extraction

## Summary

This skill enables precise, high-quality image-to-Excalidraw conversions by:
1. Analyzing images with vision capabilities
2. Mapping to appropriate Excalidraw elements
3. Generating custom SVG when needed
4. Preserving layout and styling
5. Outputting valid, ready-to-use JSON

Always prioritize accuracy, usability, and user guidance throughout the conversion process.
