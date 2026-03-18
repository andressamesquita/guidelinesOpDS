### HelperText

**Purpose**: Display contextual help or feedback messages with icons indicating severity levels for user guidance. Semantically, it represents a status message, enhancing form usability without specific roles unless in error contexts.

**Structure**: Render the `HelperText` component with a message string. Commonly integrated with inputs, buttons, or forms in interfaces. Frequently used alongside labels, checkboxes, or selects for validation or tips.

**Usage Notes**:
- Position below inputs; it includes icon and text.
- Use for guidance or errors; choose severity appropriately.
- Correct: Use for form help or warnings. Incorrect: Use for primary content or long text.
- Ensure icons match severity; customize size for layout.
- Integrate with form validation.

**HelperText Props**:
- `helperText`: String - The message text.
- `severity`: "info" | "warning" | "critical" | "success" (default: "info") - Message type with icon.
- `size`: "sm" | "md" | "lg" (default: "md") - Text and icon size.
- `className`: String - Additional styles.
- All InputHTMLAttributes<HTMLDivElement> props (excluding size).

**Example**:
```typescript
import { HelperText } from "@/components/HelperText";

function HelperTextExample() {
  return (
    <HelperText
      helperText="This field is required"
      severity="critical"
      size="md"
    />
  );
}
```