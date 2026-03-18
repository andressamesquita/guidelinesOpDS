### Label

**Purpose**: Display text labels for form elements or sections, providing context and improving accessibility. Semantically, it represents a label using the label element for accessibility, associating with inputs.

**Structure**: Render the `Label` component with a label string. Commonly integrated with inputs, checkboxes, or selects in forms. Frequently used alongside helper text or icons for form guidance.

**Usage Notes**:
- Position above inputs; it handles font and spacing.
- Use for form fields; keep concise.
- Correct: Use for input labels. Incorrect: Use for headings or body text.
- Ensure association with form elements; customize size for hierarchy.
- Integrate with form validation.

**Label Props**:
- `label`: String - The label text.
- `size`: "sm" | "md" | "lg" (default: "md") - Text size.

**Example**:
```typescript
import { Label } from "@/components/Label";

function LabelExample() {
  return (
    <Label label="Email" size="md" />
  );
}
```