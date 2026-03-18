### Drawer

**Purpose**: Provide a collapsible sidebar for navigation, displaying menu items, profile info, and allowing expansion/collapse for space management. Semantically, it represents a navigation landmark using role="navigation" for accessibility, enabling keyboard navigation and screen reader support.

**Structure**: Render the `Drawer` component with arrays of `mainItems` and `bottomItems` (each a `DrawerItem`), optional profile, and toggle handler. Commonly integrated with page layouts, headers, or content areas in dashboards. Frequently used alongside buttons, icons, or routers for app navigation.

**Usage Notes**:
- Position fixed on left or right; adjust main content margin accordingly.
- Use for multi-section apps; toggle for responsive design.
- Correct: Use for sidebar nav with icons and labels. Incorrect: Use for temporary overlays or non-nav content.
- Ensure icons are meaningful; use active states for current page.
- Animate transitions smoothly; handle state externally if needed.

**Drawer Props**:
- `mainItems`: DrawerItem[] - Array of primary navigation items.
- `bottomItems`: DrawerItem[] - Array of secondary items (e.g., settings).
- `isExpanded`: Boolean - Initial expanded state.
- `onToggleDrawer`: Function - Callback for toggle events.
- `profile`: Profile - Object with name, role, roleColor, image.
- `position`: "left" | "right" (default: "left") - Sidebar position.
- `className`: String - Additional CSS classes.

**DrawerItem Type**:
- `icon`: IconNameRender | ReactElement - Icon for the item.
- `label`: String - Text label.
- `onClick`: Function - Click handler.
- `isActive`: Boolean - Active state.

**Profile Type**:
- `name`: String - User name.
- `role`: String - User role.
- `roleColor`: String - Color for role badge.
- `image`: String - Profile image URL.

**Example**:
```typescript
import { Drawer } from "@/components/Drawer";

const items = [
  { icon: "Home", label: "Home", onClick: () => {}, isActive: true },
  { icon: "Settings", label: "Settings", onClick: () => {} }
];

function DrawerExample() {
  return (
    <Drawer
      mainItems={items}
      profile={{ name: "John Doe", role: "Admin", roleColor: "#blue", image: "avatar.jpg" }}
      isExpanded={true}
      onToggleDrawer={(expanded) => console.log(expanded)}
    />
  );
}
```
````