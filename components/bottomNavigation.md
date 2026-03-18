### BottomNavigation

**Purpose**: Provide bottom navigation for mobile interfaces, displaying icons and labels for quick access to main sections. Semantically, it represents navigation using role="navigation" for accessibility, enabling touch and keyboard navigation.

**Structure**: Render the `BottomNavigation` component with an array of `items`, each with icon, label, and click handler. Commonly integrated with page views, drawers, or tabs in mobile apps. Frequently used alongside top bars or content areas for consistent navigation.

**Usage Notes**:
- Position fixed at the bottom; adjust content padding.
- Use for 3-5 items; icons must be clear.
- Correct: Use for app sections like Home, Search. Incorrect: Use for sub-menus or desktop.
- Ensure active state; use onClick for routing.
- Customize icons and labels for branding.

**BottomNavigation Props**:
- `items`: Array of { isActive: boolean, label: string, icon: IconNameRender | ReactElement, onClick?: Function } - Navigation items.

**Example**:
```typescript
import { BottomNavigation } from "@/components/BottomNavigation";

const items = [
  { isActive: true, label: "Home", icon: "Home", onClick: () => {} },
  { isActive: false, label: "Search", icon: "Search", onClick: () => {} }
];

function BottomNavigationExample() {
  return (
    <BottomNavigation items={items} />
  );
}
```