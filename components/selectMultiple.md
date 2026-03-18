### SelectMultiple

**Purpose**: Allow users to select multiple options from a dropdown list, displaying selected items with checkboxes and supporting validation states. Semantically, it represents a multi-select using role="listbox" and aria-multiselectable for accessibility, enabling keyboard navigation and screen reader support.

**Structure**: Use `SelectMultipleRoot` for state, `SelectTrigger` for the button, `SelectMultipleContent` for the dropdown, and `SelectMultipleCheckboxItem` for options. Commonly integrated with forms, filters, or settings panels. Frequently used alongside tags, buttons, or inputs for multi-choice selections.

**Usage Notes**:
- Add padding around the trigger for better layout; content positions automatically.
- Use for multiple selections; show selected count or labels.
- Correct: Use for filters or tags. Incorrect: Use for single select or large lists without search.
- Ensure placeholder and labels; use variant for error states.
- Customize with icons and helper text; handle ellipsis for long labels.

**SelectMultiple Props**:
- `label`: String - Field label.
- `placeholder`: String - Placeholder text.
- `leftIcon`: IconNameRender | ReactElement - Left icon.
- `rightIcon`: IconNameRender | ReactElement - Right icon.
- `disabled`: Boolean - Disables the select.
- `checkboxItems`: Array of {label: string, onChecked?: Function} - Options.
- `size`: "sm" | "md" | "lg" (default: "md") - Size.
- `variant`: "success" | "warning" | "critical" | "default" (default: "warning") - Border variant.
- `maxCharsBeforeEllipsis`: Number (default: 18) - Max chars before ellipsis.
- `className`: String - Additional styles.
- `helperText`: String - Helper message.
- `defaultValues`: String[] - Initial selected values.

**SelectMultipleRoot Props**:
- All Radix DropdownMenu.Root props.

**SelectMultipleTrigger Props**:
- All Radix DropdownMenu.Trigger props.

**SelectMultipleContent Props**:
- All Radix DropdownMenu.Content props.

**SelectMultipleCheckboxItem Props**:
- All Radix DropdownMenu.CheckboxItem props.

**SelectMultipleGroup Props**:
- All Radix DropdownMenu.Group props.

**SelectMultipleSeparator Props**:
- All Radix DropdownMenu.Separator props.

**Example**:
```typescript
import { SelectMultiple } from "@/components/SelectMultiple";

function SelectMultipleExample() {
  const items = [
    { label: "Option 1", onChecked: (checked) => console.log(checked) },
    { label: "Option 2" }
  ];

  return (
    <SelectMultiple
      label="Select Options"
      placeholder="Choose..."
      checkboxItems={items}
      helperText="Select multiple"
    />
  );
}
```