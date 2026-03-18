### Dialog

**Purpose**: Display modal overlays for user interactions like confirmations, forms, or alerts, blocking the main content until dismissed. Semantically, it represents a dialog using role="dialog" and aria-modal for accessibility, ensuring focus management and screen reader support.

**Structure**: Use `DialogRoot` for state management, `DialogTrigger` to open, `DialogContent` for the modal body, with optional `DialogHeader`, `DialogTitle`, `DialogDescription`, `DialogFooter`. Commonly integrated with buttons, forms, or alerts in workflows requiring user attention. Frequently used alongside inputs, buttons, or action sheets for confirmations.

**Usage Notes**:
- Position dialogs centered; they include overlay and animations.
- Use for important actions like deletions or settings; avoid for non-blocking info.
- Correct: Use for confirmations with cancel/confirm buttons. Incorrect: Use for simple tooltips or persistent content.
- Ensure keyboard dismissal (escape); trap focus inside.
- Customize footer for actions; use DialogClose for manual close.

**Dialog Props** (from index.tsx):
- `open`: Boolean - Controls visibility.
- `onOpenChange`: Function - Callback for open state changes.
- `title`: String - Modal title.
- `children`: ReactElement - Modal body content.
- `onCancel`: Function - Cancel button handler.
- `cancelLabel`: String (default: "Cancelar") - Cancel button text.
- `onConfirm`: Function - Confirm button handler.
- `confirmLabel`: String (default: "Confirmar") - Confirm button text.

**DialogRoot Props**:
- All Radix Dialog.Root props.

**DialogTrigger Props**:
- All Radix Dialog.Trigger props.

**DialogContent Props**:
- All Radix Dialog.Content props.

**DialogHeader Props**:
- All div props.

**DialogTitle Props**:
- All Radix Dialog.Title props.

**DialogDescription Props**:
- All Radix Dialog.Description props.

**DialogFooter Props**:
- All div props.

**DialogClose Props**:
- All Radix Dialog.Close props.

**Example**:
```typescript
import { Dialog } from "@/components/Dialog";

function DialogExample() {
  const [open, setOpen] = useState(false);

  return (
    <Dialog
      open={open}
      onOpenChange={setOpen}
      title="Confirm Action"
      onCancel={() => setOpen(false)}
      onConfirm={() => alert("Confirmed")}
    >
      <p>Are you sure?</p>
    </Dialog>
  );
}
```