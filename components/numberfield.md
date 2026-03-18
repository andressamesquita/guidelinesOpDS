### NumberField

**Purpose**: Allow users to input numeric values with increment and decrement buttons for easy adjustment, supporting validation and helper text. Semantically, it represents a numeric input using type="number" and role="spinbutton" for accessibility, enabling keyboard navigation and screen reader support.

**Structure**: Render the `NumberField` component with label, value, and optional helper text. Commonly integrated with forms, dialogs, or settings panels. Frequently used alongside buttons, selects, or other inputs for data entry.

**Usage Notes**:
- Add padding around the field for better layout; it includes buttons and input.
- Use for quantities or counts; set min/max for validation.
- Correct: Use for age, quantity inputs. Incorrect: Use for free text or non-numeric data.
- Ensure buttons are accessible; disable if needed.
- Show helper text for guidance; use variant for error states.

**NumberField Props**:
- `label`: String - Field label.
- `size`: "sm" | "md" | "lg" (default: "md") - Field size.
- `value`: Number (default: 0) - Initial value.
- `variant`: String - Border variant (e.g., "default", "error").
- `helperText`: String - Helper message.
- `disabled`: Boolean - Disables the field.
- `maxLength`: Number - Max characters.
- All standard input props (e.g., min, max, step).

**Example**:
```typescript
import { NumberField } from "@/components/NumberField";

function NumberFieldExample() {
  const [value, setValue] = useState(5);

  return (
    <NumberField
      label="Quantity"
      value={value}
      onChange={(e) => setValue(Number(e.target.value))}
      min={0}
      max={10}
      helperText="Enter a number between 0 and 10"
    />
  );
}
```