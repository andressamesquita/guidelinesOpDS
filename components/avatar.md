### Avatar

**Purpose**: Display user profiles or entities with images, initials, or icons, often representing individuals in lists, comments, or navigation. Semantically, it represents a visual identifier for users or objects, enhancing recognition and personalization.

**Structure**: Render the `Avatar` component with optional image source, fallback text, and indicators. Commonly integrated with user lists, comments, navigation bars, or cards. Frequently used alongside text, buttons, or badges for user interfaces.

**Usage Notes**:
- Use for user representations in social features, profiles, or team sections.
- Choose appropriate size based on context: smaller for lists, larger for profiles.
- Correct: Use with status indicators for online presence. Incorrect: Use for non-user entities without fallback.
- Ensure alt text for accessibility when using images.
- Borders add emphasis; use dashed for special cases like placeholders.

**Avatar Props**:
- `src`: String - Image URL for the avatar.
- `alt`: String - Alt text for the image.
- `fallback`: String - Text to display if image fails (e.g., initials).
- `size`: "sm" | "md" | "lg" | "xl" | "2xl" (default: "md") - Controls avatar dimensions.
- `status`: "online" | "offline" | "away" - Shows status indicator ball.
- `indicatorIcon`: "status" | "settings" (default: "status") - Type of indicator.
- `withBorder`: Boolean (default: true) - Whether to show a border.
- `borderStyle`: "solid" | "dashed" (default: "solid") - Border style.

**Example**:
```typescript
import { Avatar } from "@/components/Avatar";

function AvatarExample() {
  return (
    <Avatar
      src="https://example.com/avatar.jpg"
      alt="User Avatar"
      fallback="JD"
      size="md"
      status="online"
      indicatorIcon="status"
      withBorder={true}
      borderStyle="solid"
    />
  );
}
```