### Combobox

**Purpose**: Provide a searchable dropdown for selecting options from a list, allowing users to type and filter results. Semantically, it represents a combobox using role="combobox" and aria-expanded for accessibility, enabling keyboard navigation and screen reader support.

**Structure**: Use `Command` as the container, `CommandInput` for search, `CommandList` for the dropdown, `CommandItem` for options, and optional `CommandEmpty`, `CommandGroup` for organization. Commonly integrated with forms, inputs, or buttons in search interfaces or settings. Frequently used alongside dialogs or modals for advanced selections.

**Usage Notes**:
- Add padding around the combobox for better spacing; it handles focus internally.
- Use for large lists where search is needed; avoid for small static lists.
- Correct: Use for searchable selects like country pickers. Incorrect: Use for binary choices without search.
- Ensure keyboard support (arrow keys, enter); show empty state when no matches.
- Group items with CommandGroup for categorization.

**Command Props**:
- All cmdk Command props - Main container.

**CommandDialog Props**:
- All DialogProps - For modal combobox.

**CommandEmpty Props**:
- All cmdk Empty props - Shown when no results.

**CommandGroup Props**:
- All cmdk Group props - Groups items.

**CommandInput Props**:
- All cmdk Input props - Search input.

**CommandList Props**:
- All cmdk List props - Scrollable list.

**CommandItem Props**:
- All cmdk Item props - Selectable option.

**Example**:
```typescript
import { Command, CommandInput, CommandList, CommandEmpty, CommandGroup, CommandItem } from "@/components/Combobox";

function ComboboxExample() {
  return (
    <Command>
      <CommandInput placeholder="Search..." />
      <CommandList>
        <CommandEmpty>No results.</CommandEmpty>
        <CommandGroup heading="Fruits">
          <CommandItem>Apple</CommandItem>
          <CommandItem>Banana</CommandItem>
        </CommandGroup>
      </CommandList>
    </Command>
  );
}
```