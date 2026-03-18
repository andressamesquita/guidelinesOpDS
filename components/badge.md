### Badge

**Purpose**: Display small labels or indicators for status, counts, or categories, with optional icons and customizable styles. Semantically, it represents a status indicator or label, enhancing readability without semantic roles unless in specific contexts.

**Structure**: Render the `Badge` component with text and optional icons. Commonly integrated with buttons, lists, or avatars in interfaces. Frequently used alongside notifications, tabs, or cards for highlighting information.

**Usage Notes**:
- Position near relevant elements; keep text short.
- Use severity for status; outline for subtle variants.
- Correct: Use for "New" or counts. Incorrect: Use for paragraphs or actions.
- Ensure contrast; customize color if needed.
- Add icons for visual cues.

**Badge Props**:
- `severity`: "default" | "success" | "warning" | "critical" (default: "default") - Color theme.
- `size`: "sm" | "md" | "lg" (default: "md") - Badge size.
- `style`: "square" | "rounded" (default: "square") - Corner style.
- `outline`: Boolean (default: false) - Outline variant.
- `leftIcon`: IconNameRender | ReactElement - Left icon.
- `rightIcon`: IconNameRender | ReactElement - Right icon.
- `color`: String - Custom color.
- All HTMLAttributes<HTMLDivElement> props.

**Example**:
```typescript
import { Badge } from "@/components/Badge";

function BadgeExample() {
  return (
    <Badge severity="success" size="md" leftIcon="Check">
      Approved
    </Badge>
  );
}
```