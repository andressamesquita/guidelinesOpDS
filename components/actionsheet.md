### ActionSheet

**Purpose**: Present a set of actions or options in a modal overlay that slides up from the bottom of the screen, allowing users to perform tasks without leaving the current context. Semantically, it represents a temporary, dismissible menu for actions like delete, share, or settings.

**Structure**: Use `ActionSheetRoot` as the container, `ActionSheetTrigger` to open it, `ActionSheetContent` for the sheet body, and optional `ActionSheetHeader`, `ActionSheetTitle`, `ActionSheetDescription`, `ActionSheetFooter` for layout. Commonly integrated with buttons, lists, or forms for triggering actions. Frequently used in mobile interfaces alongside navigation bars or cards.

**Usage Notes**:
- Add padding inside the content for better readability; the sheet itself has minimal styling.
- Use the overlay for backdrop dismissal; ensure it's accessible.
- Correct: Use for action menus on mobile. Incorrect: Use for complex forms or large content that requires scrolling.
- Include a close button in the footer for better UX.
- Do not overload with too many actions; limit to 5-7 for clarity.

**ActionSheetRoot Props**:
- All props from `vaul.Drawer.Root`, such as `open`, `onOpenChange`, `shouldScaleBackground`.

**ActionSheetTrigger Props**:
- All props from `vaul.Drawer.Trigger`.
- `children`: ReactNode (trigger element, e.g., a button).

**ActionSheetPortal Props**:
- All props from `vaul.Drawer.Portal`.

**ActionSheetOverlay Props**:
- All props from `vaul.Drawer.Overlay`.
- `className`: String for additional styling.

**ActionSheetContent Props**:
- All props from `vaul.Drawer.Content`, plus `hasHandler` (boolean for drag handle, default true).
- `children`: ReactNode (sheet content).
- `className`: String for additional styling.

**ActionSheetClose Props**:
- All props from `vaul.Drawer.Close`.
- `children`: ReactNode (close trigger).

**ActionSheetHeader Props**:
- Standard div props.
- `className`: String for additional styling.

**ActionSheetTitle Props**:
- All props from `vaul.Drawer.Title`.
- `className`: String for additional styling.

**ActionSheetDescription Props**:
- All props from `vaul.Drawer.Description`.
- `className`: String for additional styling.

**ActionSheetFooter Props**:
- Standard div props.
- `className`: String for additional styling.

**Example**:
```typescript
import { ActionSheetRoot, ActionSheetTrigger, ActionSheetContent, ActionSheetHeader, ActionSheetTitle, ActionSheetFooter, ActionSheetClose } from "@/components/ActionSheet";

function ActionSheetExample() {
  return (
    <ActionSheetRoot>
      <ActionSheetTrigger asChild>
        <button>Open Actions</button>
      </ActionSheetTrigger>
      <ActionSheetContent>
        <ActionSheetHeader>
          <ActionSheetTitle>Actions</ActionSheetTitle>
        </ActionSheetHeader>
        <div className="p-4">
          <button>Action 1</button>
          <button>Action 2</button>
        </div>
        <ActionSheetFooter>
          <ActionSheetClose asChild>
            <button>Cancel</button>
          </ActionSheetClose>
        </ActionSheetFooter>
      </ActionSheetContent>
    </ActionSheetRoot>
  );
}
```