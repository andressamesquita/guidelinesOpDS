### Card

**Purpose**: Group related content in a styled container with customizable backgrounds, borders, and padding for visual separation. Semantically, it represents a section or article using role="region" if needed, enhancing content organization.

**Structure**: Render the `Card` component with children content. Commonly integrated with images, text, or buttons in dashboards or lists. Frequently used alongside grids, modals, or forms for content presentation.

**Usage Notes**:
- Add padding inside for content spacing; it provides background and border.
- Use variants for emphasis; customize colors for branding.
- Correct: Use for product cards or info blocks. Incorrect: Use for page layout or single elements.
- Ensure contrast; use padding for readability.
- Integrate with other components for rich content.

**Card Props**:
- `variant`: "solid" | "outline" | "ghost" (default: "solid") - Card style.
- `padding`: "none" | "sm" | "md" | "lg" | "mobile" (default: "sm") - Internal padding.
- `color`: OpalaColor (default: "opala.strong.default") - Background color for solid.
- `borderColor`: OpalaColor - Border color for outline.
- All HTMLAttributes<HTMLDivElement> props.

**Example**:
```typescript
import { Card } from "@/components/Card";

function CardExample() {
  return (
    <Card variant="solid" padding="md" color="opala.primary.default">
      <h3>Title</h3>
      <p>Content</p>
    </Card>
  );
}
```