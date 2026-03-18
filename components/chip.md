### Chip

**Purpose**: Display selectable tags or filters with icons and colors, allowing users to toggle states for filtering or categorization. Semantically, it represents a button using role="button" for accessibility, enabling keyboard navigation and screen reader support.

**Structure**: Render the `Chip` component with label and optional icons. Commonly integrated with lists, filters, or inputs in interfaces. Frequently used alongside dropdowns, selects, or cards for tagging.

**Usage Notes**:
- Add padding around for better layout; it handles selection state.
- Use for filters or tags; limit text length.
- Correct: Use for category filters. Incorrect: Use for actions or long text.
- Ensure icons enhance meaning; use variant for status.
- Customize colors and sizes for branding.

**Chip Props**:
- `variant`: "default" | "success" | "warning" | "critical" (default: "default") - Color theme.
- `size`: "sm" | "md" | "lg" (default: "md") - Chip size.
- `leftIcon`: IconNameRender | ReactElement - Left icon.
- `rightIcon`: IconNameRender | ReactElement - Right icon.
- `label`: String - Chip text.
- `disabled`: Boolean - Disables interaction.
- `onClick`: Function - Click handler.

**Example**:
```typescript
import { Chip } from "@/components/Chip";

function ChipExample() {
  return (
    <Chip
      variant="success"
      size="md"
      label="Active"
      leftIcon="Check"
      onClick={() => alert("Selected")}
    />
  );
}
```