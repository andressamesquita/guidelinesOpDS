### Select

**Purpose**: Allow users to choose a single option from a dropdown list, with support for labels, icons, and validation states. Semantically, it represents a select using role="combobox" and aria-expanded for accessibility, enabling keyboard navigation and screen reader support.

**Structure**: Use `SelectRoot` for state, `SelectTrigger` for the button, `SelectContent` for the dropdown, and `SelectItem` for options. Commonly integrated with forms, filters, or settings panels. Frequently used alongside inputs, buttons, or labels for data selection.

**Usage Notes**:
- Add padding around the trigger for better layout; content positions automatically.
- Use for single selections; limit items for usability.
- Correct: Use for dropdowns like country or category. Incorrect: Use for multi-select or searchable lists.
- Ensure placeholder and labels; use variant for error states.
- Customize with icons and helper text.

**SelectRoot Props**:
- All Radix Select.Root props, plus `placeholder`, `leftIcon`, `rightIcon`, `items`, `label`, `variant`, `helperText`, `size`, `containerClassName`.

**SelectTrigger Props**:
- All Radix Select.Trigger props.

**SelectContent Props**:
- All Radix Select.Content props, plus `position`.

**SelectItem Props**:
- All Radix Select.Item props.

**SelectLabel Props**:
- All Radix Select.Label props.

**SelectSeparator Props**:
- All Radix Select.Separator props.

**SelectScrollUpButton Props**:
- All Radix Select.ScrollUpButton props.

**SelectScrollDownButton Props**:
- All Radix Select.ScrollDownButton props.

**SelectGroup Props**:
- All Radix Select.Group props.

**SelectValue Props**:
- All Radix Select.Value props.

**Example**:
```typescript
import { SelectRoot, SelectTrigger, SelectContent, SelectItem, SelectValue } from "@/components/Select";

function SelectExample() {
  return (
    <SelectRoot>
      <SelectTrigger>
        <SelectValue placeholder="Select an option" />
      </SelectTrigger>
      <SelectContent>
        <SelectItem value="option1">Option 1</SelectItem>
        <SelectItem value="option2">Option 2</SelectItem>
      </SelectContent>
    </SelectRoot>
  );
}
```