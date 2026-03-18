### IconRenderer

**Purpose**: Display scalable vector icons from the Lucide library or custom React elements for visual enhancement and communication in interfaces. Semantically, icons can be decorative or meaningful, using aria-hidden or aria-label as needed for accessibility.

**Structure**: Render the `IconRenderer` component with an icon as a string name or ReactElement. Commonly integrated with buttons, labels, or navigation in interfaces. Frequently used alongside text, badges, or chips for visual cues.

**Usage Notes**:
- Add padding around if needed; it renders SVG or custom element.
- Use for actions or status; choose meaningful icons.
- Correct: Use for button icons or status. Incorrect: Use for text or complex graphics.
- Ensure accessibility; use color for emphasis.
- Customize size and color for branding; supports custom elements.

**IconRenderer Props**:
- `icon`: IconNameRender | ReactElement - Icon name or custom element.
- `color`: String - Icon color.
- `size`: Number - Icon size in pixels.
- All LucideProps (excluding name) - Additional props.

**Example**:
```typescript
import { IconRenderer } from "@/components/IconRenderer";

function IconRendererExample() {
  return (
    <IconRenderer icon="Home" color="blue" size={24} />
  );
}
```