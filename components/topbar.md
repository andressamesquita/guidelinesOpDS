### TopBar

**Purpose**: Provide a top navigation bar with search functionality, left and right content areas, and responsive design for mobile and desktop. Semantically, it represents a header using role="banner" for accessibility, enabling navigation and search interactions.

**Structure**: Render the `TopBar` component with optional left/right children, search field, and additional rows on desktop. Commonly integrated with navigation menus, buttons, or avatars in app layouts. Frequently used alongside drawers, tabs, or content areas for consistent navigation.

**Usage Notes**:
- Position fixed at the top; adjust main content margin.
- Use for app headers; enable search for global queries.
- Correct: Use for dashboards or apps. Incorrect: Use for page-specific headers or footers.
- Ensure responsive design; customize rows for branding.
- Integrate with routing for navigation.

**TopBar Props**:
- `childrenLeft`: ReactNode - Left side content (e.g., logo, menu).
- `childrenRight`: ReactNode - Right side content (e.g., profile, actions).
- `hasTextField`: Boolean (default: true) - Show search field.
- `searchFieldProps`: Omit<SearchFieldProps, "className"> - Props for search field.
- `className`: String - Additional styles.
- `hasTopRow`: Boolean (default: false) - Show top row on desktop.
- `topRow`: ReactNode - Content for top row.
- `hasBottomRow`: Boolean (default: false) - Show bottom row on desktop.
- `bottomRow`: ReactNode - Content for bottom row.

**Example**:
```typescript
import { TopBar } from "@/components/TopBar";

function TopBarExample() {
  return (
    <TopBar
      childrenLeft={<div>Logo</div>}
      childrenRight={<button>Profile</button>}
      hasTextField={true}
      searchFieldProps={{ placeholder: "Search..." }}
      hasTopRow={true}
      topRow={<div>Top Content</div>}
    />
  );
}
```