### List

**Purpose**: Display a collection of items in a structured list format, supporting variants for profiles, notifications, or menus with optional avatars, icons, and actions. Semantically, it represents a list using role="list" for accessibility, enabling keyboard navigation and screen reader support.

**Structure**: Render the `List` component with an array of `items` and a `variant` for styling. Commonly integrated with avatars, switches, or icons in dashboards or settings. Frequently used alongside buttons, dialogs, or navigation for user interactions.

**Usage Notes**:
- Add padding around the list for better spacing; it handles item layout.
- Choose variant based on content: profile for users, notification for alerts, menu for actions.
- Correct: Use for user lists or menu options. Incorrect: Use for single items or non-list content.
- Ensure clickable items have onClick; use disabled for inactive states.
- Customize with icons and switches for interactivity.

**List Props**:
- `items`: ListItem[] - Array of list items.
- `variant`: "profile" | "notification" | "menu" (default: "profile") - List style.
- `className`: String - Additional CSS classes.

**ListItem Type**:
- `avatar`: String - Avatar image URL.
- `initials`: String - Fallback initials.
- `icon`: IconNameRender | ReactElement - Left icon.
- `title`: String - Main text.
- `subtitle`: String - Secondary text.
- `timestamp`: String - Time info.
- `onClick`: Function - Click handler.
- `disabled`: Boolean - Disables item.
- `highlight`: Boolean - Highlight state.
- `focus`: Boolean - Focus state.
- `onSwitch`: Function - Switch change handler.
- `checked`: Boolean - Switch state.
- `rightIcon`: IconNameRender | ReactElement - Right icon.
- `status`: String - Status indicator.

**Example**:
```typescript
import { List } from "@/components/List";

const items = [
  {
    avatar: "avatar.jpg",
    initials: "JD",
    title: "John Doe",
    subtitle: "Admin",
    onClick: () => alert("Clicked"),
    rightIcon: "ChevronRight"
  }
];

function ListExample() {
  return (
    <List items={items} variant="profile" />
  );
}
```