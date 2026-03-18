### Tabs

**Purpose**: Organize content into multiple panels accessed via tabs, allowing users to switch between related sections without leaving the page.

**Structure**: Use `TabsRoot` for state, `TabsList` for the tab strip, `TabsTrigger` for each tab button, and `TabsContent` for panel content. Commonly integrated with content areas, forms, or dashboards. Frequently used alongside buttons, icons, or badges for enhanced UX.

**Usage Notes**:
- Add padding around the tabs for better spacing; it handles active states.
- Use for related content; limit tabs for clarity.
- Correct: Use for settings or views. Incorrect: Use for navigation or unrelated content.
- Ensure icons and badges enhance usability; avoid overloading.
- Customize with className for styling.

**Tabs Props**:
- `defaultTab`: String - Initial active tab value.
- `tabs`: Tabs[] - Array of tab objects.

**Tabs Type**:
- `value`: String - Unique tab identifier.
- `title`: String - Tab label.
- `icon`: IconName | ReactElement - Optional icon.
- `content`: ReactElement - Panel content.
- `badgeProps`: BadgeProps - Optional badge.

**TabsRoot Props**:
- All Radix Tabs.Root props.

**TabsList Props**:
- All Radix Tabs.List props.

**TabsTrigger Props**:
- All Radix Tabs.Trigger props.

**TabsContent Props**:
- All Radix Tabs.Content props.

**Example**:
```typescript
import { Tabs } from "@/components/Tabs";

const tabs = [
  { value: "tab1", title: "Tab 1", content: <div>Content 1</div> },
  { value: "tab2", title: "Tab 2", icon: "Settings", content: <div>Content 2</div> }
];

function TabsExample() {
  return (
    <Tabs defaultTab="tab1" tabs={tabs} />
  );
}
```