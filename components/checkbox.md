### Checkbox

**Purpose**: Allow users to select or deselect options, with support for labels, descriptions, and helper text for clarity. Semantically, it represents a checkbox using role="checkbox" for accessibility, enabling keyboard navigation and screen reader support.

**Structure**: Render the `Checkbox` component with optional label, description, and helper text. Commonly integrated with forms, lists, or settings panels. Frequently used alongside radio buttons, selects, or buttons for multi-choice inputs.

**Usage Notes**:
- Add padding around for better layout; it includes check icon and text.
- Use for binary choices; group for multiple.
- Correct: Use for agreements or filters. Incorrect: Use for single selections or long lists.
- Ensure labels for accessibility; use disabled for inactive states.
- Customize size and helper text for UX.

**Checkbox Props**:
- `checked`: Boolean (default: false) - Checked state.
- `onChange`: Function - Change handler.
- `className`: String - Additional styles.
- `helperText`: String - Helper message with icon.
- `label`: String - Main label.
- `description`: String - Subtitle.
- `size`: "sm" | "md" | "lg" (default: "md") - Checkbox size.
- `disabled`: Boolean (default: false) - Disables interaction.
- `readonly`: Boolean (default: false) - Read-only state.

**Example**:
```typescript
import { Checkbox } from "@/components/Checkbox";

function CheckboxExample() {
  const [checked, setChecked] = useState(false);

  return (
    <Checkbox
      checked={checked}
      onChange={setChecked}
      label="Agree to terms"
      description="Accept the conditions"
      helperText="Required field"
    />
  );
}
```