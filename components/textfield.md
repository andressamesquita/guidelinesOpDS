### TextField

**Purpose**: Allow users to input text with optional icons, mic button for voice input, helper text, and character counting for validation. Semantically, it represents a text input using role="textbox" for accessibility, enabling keyboard navigation and screen reader support.

**Structure**: Render the `TextField` component with label and optional icons, mic, and helper text. Commonly integrated with forms, dialogs, or search bars. Frequently used alongside buttons, selects, or alerts for data entry.

**Usage Notes**:
- Add padding around the field for better layout; it includes icons and input.
- Use for text inputs; enable mic for voice.
- Correct: Use for names or messages. Incorrect: Use for numbers or selections.
- Ensure labels and helper text for guidance; use variant for error states.
- Customize with icons and maxLength for constraints.

**TextField Props**:
- `label`: String - Field label.
- `hasMic`: Boolean (default: false) - Show mic button.
- `size`: "sm" | "md" | "lg" (default: "md") - Field size.
- `variant`: "default" | "error" etc. (default: "default") - Border variant.
- `disabled`: Boolean (default: false) - Disables the field.
- `leftIcon`: IconNameRender | ReactElement - Left icon.
- `rightIcon`: IconNameRender | ReactElement - Right icon.
- `contentClassName`: String - Input container styles.
- `containerClassName`: String - Outer container styles.
- `helperText`: String - Helper message.
- `onMicClick`: Function - Mic button handler.
- All standard input props (e.g., type, onChange, maxLength).

**Example**:
```typescript
import { TextField } from "@/components/TextField";

function TextFieldExample() {
  const [value, setValue] = useState("");

  return (
    <TextField
      label="Name"
      value={value}
      onChange={(e) => setValue(e.target.value)}
      helperText="Enter your name"
      maxLength={50}
      hasMic={true}
      onMicClick={() => alert("Voice input")}
    />
  );
}
```