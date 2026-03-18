### Alert

**Purpose**: Display important messages or notifications to users, such as errors, warnings, successes, or informational alerts. Semantically, it represents a status update or feedback, using role="alert" for accessibility, and helps guide user attention without interrupting the flow.

**Structure**: Render the `Alert` component with optional title, description, and props for severity and size. Commonly integrated with forms, buttons, or modals for validation feedback, or alongside banners and toasts for system notifications. Frequently used in dashboards, error pages, or after user actions.

**Usage Notes**:
- Position alerts prominently, such as at the top of pages or near relevant content.
- Use appropriate severity for context: info for neutral info, warning for cautions, critical for errors, success for confirmations.
- Correct: Use for temporary feedback like form errors. Incorrect: Use for persistent content or as a replacement for dialogs.
- Ensure icons are shown by default for visual cues; hide only if space is limited.
- Include close button for dismissible alerts to improve UX.

**Alert Props**:
- `severity`: "info" | "warning" | "critical" | "success" (default: "info") - Determines icon and color scheme.
- `size`: "sm" | "md" | "lg" (default: "md") - Controls overall size and icon dimensions.
- `title`: String - Optional heading text.
- `description`: ReactNode - Optional body content.
- `showIcon`: Boolean (default: true) - Whether to display the severity icon.
- `closeButton`: Boolean (default: true) - Whether to show the close button.
- `open`: Boolean (default: true) - Controls visibility; set to false to hide.
- `onClose`: Function - Callback when close button is clicked.
- `className`: String - Additional CSS classes.

**Example**:
```typescript
import { Alert } from "@/components/Alert";

function AlertExample() {
  return (
    <Alert
      severity="critical"
      size="md"
      title="Error Occurred"
      description="Something went wrong. Please try again."
      onClose={() => console.log("Closed")}
    />
  );
}
```