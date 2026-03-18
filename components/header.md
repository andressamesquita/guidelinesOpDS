### Header

**Purpose**: Display page title, subtitle, description, and navigation elements like breadcrumbs and badges for context and orientation. Semantically, it represents a header using role="banner" for accessibility, providing page information and navigation.

**Structure**: Render the `Header` component with title, optional subtitle, description, and breadcrumb. Commonly integrated with content areas, sidebars, or footers in page layouts. Frequently used alongside separators, badges, or buttons for enhanced UX.

**Usage Notes**:
- Position at the top of pages; it includes breadcrumb and separator.
- Use for page context; keep concise.
- Correct: Use for article or dashboard headers. Incorrect: Use for footers or non-page content.
- Ensure breadcrumbs for navigation; customize badges for status.
- Integrate with routing for breadcrumbs.

**Header Props**:
- `title`: String - Main title.
- `subtitle`: String - Subtitle.
- `description`: String - Description text.
- `auxiliaryText`: String - Additional text.
- `className`: String - Additional styles.
- `breadCrumbProps`: BreadcrumbProps - Breadcrumb configuration.
- `textTitleBadge`: String - Title badge text.
- `titleBadgeProps`: BadgeProps - Title badge props.
- `textFooterBadge`: String - Footer badge text.
- `footerBadgeProps`: BadgeProps - Footer badge props.
- All HTMLAttributes<HTMLDivElement> props.

**Example**:
```typescript
import { Header } from "@/components/Header";

function HeaderExample() {
  return (
    <Header
      title="Dashboard"
      subtitle="Overview"
      description="Main metrics"
      breadCrumbProps={{ /* breadcrumb props */ }}
      textTitleBadge="New"
      titleBadgeProps={{ severity: "success" }}
      auxiliaryText="Updated"
      textFooterBadge="Active"
      footerBadgeProps={{ severity: "default" }}
    />
  );
}
```