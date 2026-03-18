### Icon

**Purpose**: Display scalable vector icons from the Lucide library for visual enhancement and communication in interfaces. Semantically, icons can be decorative or meaningful, using aria-hidden or aria-label as needed for accessibility.

**Structure**: Render the `Icon` component with a name from Lucide icons. Commonly integrated with buttons, labels, or navigation in interfaces. Frequently used alongside text, badges, or chips for visual cues.

**Usage Notes**:
- Add padding around if needed; it renders SVG.
- Use for actions or status; choose meaningful icons.
- Correct: Use for button icons or status. Incorrect: Use for text or complex graphics.
- Ensure accessibility; use color for emphasis.
- Customize size and color for branding.

**Icon Props**:
- `name`: IconName - Name of the Lucide icon.
- `color`: String - Icon color.
- `size`: Number - Icon size in pixels.
- All LucideProps - Additional Lucide icon props.

**Example**:
```typescript
import { Icon } from "@/components/Icon";

function IconExample() {
  return (
    <Icon name="Home" color="blue" size={24} />
  );
}
```