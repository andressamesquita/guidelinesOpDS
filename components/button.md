### Button

**Purpose**: Enable user interactions such as submitting forms, triggering actions, or navigating, providing clear calls-to-action. Semantically, it represents an interactive element using the button role, ensuring accessibility for clicks and keyboard navigation.

**Structure**: Render the `Button` component with text, optional icons, and props for variant and color. Commonly integrated with forms, modals, cards, or navigation bars. Frequently used alongside inputs, alerts, or other buttons in toolbars.

**Usage Notes**:
- Use primary color for main actions; secondary for less important ones.
- Variants: solid for emphasis, outline for secondary, ghost for subtle.
- Correct: Use for actions like "Save" or "Submit". Incorrect: Use for links without action.
- Ensure sufficient contrast and size for accessibility.
- Add loading states or disable for pending actions.

**Button Props**:
- `variant`: "solid" | "outline" | "ghost" - Button style.
- `color`: "primary" | "success" | "warning" | "critical" - Color theme.
- `size`: String (e.g., "sm", "md", "lg") - Button size.
- `disabled`: Boolean - Disables interaction.
- `children`: ReactNode - Button content.
- `onClick`: Function - Click handler.
- `className`: String - Additional styles.

**Example**:
```typescript
import { Button } from "@/components/Button";

function ButtonExample() {
  return (
    <Button variant="solid" color="primary" onClick={() => alert("Clicked")}>
      Submit
    </Button>
  );
}
```