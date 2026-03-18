### Dropdown

**Purpose**: Display a contextual menu of actions or options triggered by a button, allowing users to select items without cluttering the UI. Semantically, it represents a menu using role="menu" for accessibility, enabling keyboard navigation and screen reader support.

**Structure**: Use `Dropdown` as the root with trigger and content, populate with `Dropdown.MenuItem`, `Dropdown.CheckboxItem`, `Dropdown.SubMenu`, or `Dropdown.Separator`. Commonly integrated with buttons, toolbars, or navigation bars in interfaces. Frequently used alongside icons, forms, or tables for actions.

**Usage Notes**:
- Position content relative to trigger; it handles portal and animations.
- Use for secondary actions; limit items for clarity.
- Correct: Use for user actions like settings or filters. Incorrect: Use for primary navigation or large data lists.
- Ensure focus management; close on selection.
- Customize with icons and descriptions for better UX.

**Dropdown Props**:
- `label`: String - Trigger button text.
- `description`: String - Optional subtitle.
- `disabled`: Boolean - Disables the dropdown.
- `leftIcon`: IconNameRender | ReactElement - Icon for trigger.
- `triggerClassName`: String - Additional trigger styles.
- `contentClassName`: String - Additional content styles.
- `children`: ReactNode - Menu items.

**Dropdown.MenuItem Props**:
- `label`: String - Item text.
- `description`: String - Optional subtitle.
- `icon`: IconNameRender | ReactElement - Item icon.
- `onClick`: Function - Click handler.
- `className`: String - Additional styles.

**Dropdown.CheckboxItem Props**:
- `label`: String - Item text.
- `description`: String - Optional subtitle.
- `icon`: IconNameRender | ReactElement - Item icon.
- `checked`: Boolean - Checked state.
- `onCheckedChange`: Function - Change handler.
- `onClick`: Function - Click handler.
- `className`: String - Additional styles.

**Dropdown.SubMenu Props**:
- `label`: String - Submenu trigger text.
- `children`: ReactNode - Submenu items.
- `triggerClassName`: String - Trigger styles.
- `contentClassName`: String - Content styles.

**Dropdown.Separator Props**:
- All Radix Separator props - Divider line.

**Example**:
```typescript
import { Dropdown } from "@/components/Dropdown";

function DropdownExample() {
  return (
    <Dropdown label="Actions" leftIcon="Settings">
      <Dropdown.MenuItem label="Edit" onClick={() => alert("Edit")} />
      <Dropdown.CheckboxItem label="Visible" checked={true} onCheckedChange={(checked) => console.log(checked)} />
      <Dropdown.Separator />
      <Dropdown.SubMenu label="More">
        <Dropdown.MenuItem label="Delete" onClick={() => alert("Delete")} />
      </Dropdown.SubMenu>
    </Dropdown>
  );
}
```