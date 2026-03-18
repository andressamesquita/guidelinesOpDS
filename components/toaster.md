### Toaster

**Purpose**: Display transient, non-blocking feedback messages (toasts) to inform users about system actions, results, or status changes.

**Semantic Role**:  
Represents ephemeral system feedback. Unlike modals or alerts, toasts do not interrupt the user’s flow and are used for lightweight, time-bound communication such as confirmations, errors, or informational updates.

---

### When to Use

Use `Toaster` when:

- Providing feedback after user actions (e.g., form submission, save, delete)
- Displaying success, error, warning, or informational messages
- Communicating background process results without interrupting the user
- पुष्टि (confirmation) messages that do not require user interaction

Commonly used with:

- Forms (submission feedback)
- Buttons and user actions (e.g., “Save”, “Delete”)
- API interactions (success/error handling)
- Notifications systems
- Global layout (mounted once at app root)

---

### Structure

The component is a wrapper around `sonner`’s `Toaster` and includes:

- Theme integration via `next-themes`
- Predefined icons for toast types (success, error, info, warning)
- Default styling aligned with design tokens
- Configurable `toastOptions` for customization

Toasts are triggered using the exported `toast` function.

---

### Usage Notes

- Mount **only once** in the application (typically at the root level).
- Use the `toast` function to trigger notifications.
- Keep messages short and clear.
- Avoid stacking too many toasts simultaneously.
- Use appropriate toast types (`success`, `error`, `info`, `warning`) for clarity.
- Do not use toasts for critical actions that require user confirmation (use modals instead).

---

### Correct Usage

✅ Mounting the toaster in the app:
```tsx
import { Toaster } from "@/components/Toaster";

function App() {
  return (
    <>
      <Toaster />
      <MainApp />
    </>
  );
}
````

✅ Triggering a success toast:

```tsx id="toast1"
import { toast } from "@/components/Toaster";

toast.success("Changes saved successfully");
```

✅ Triggering an error toast:

```tsx id="toast2"
toast.error("Something went wrong");
```

✅ With action:

```tsx id="toast3"
toast("File deleted", {
  action: {
    label: "Undo",
    onClick: () => console.log("Undo action"),
  },
});
```

---

### Incorrect Usage

❌ Mounting multiple toasters:

```tsx id="toast4"
<>
  <Toaster />
  <Toaster />
</>
```

❌ Using toast for critical confirmation:

```tsx id="toast5"
toast("Are you sure you want to delete?");
```

❌ Overloading with too many messages:

```tsx id="toast6"
toast.success("Saved");
toast.success("Updated");
toast.success("Synced");
toast.success("Done");
```

❌ Long or unclear messages:

```tsx id="toast7"
toast("The operation you attempted to perform has been completed with partial success and requires further validation.");
```

---

### API

#### `Toaster Props`

Extends: `React.ComponentProps<typeof Sonner>`

| Prop           | Type                            | Default           | Description                                             |
| -------------- | ------------------------------- | ----------------- | ------------------------------------------------------- |
| `theme`        | `"light" \| "dark" \| "system"` | `"system"`        | Controls the visual theme of the toaster                |
| `toastOptions` | `object`                        | Custom default    | Default configuration for all toasts (styles, behavior) |
| `className`    | `string`                        | `"toaster group"` | Custom class for the toaster container                  |
| `icons`        | `object`                        | predefined        | Custom icons for each toast type                        |
| `...props`     | `Sonner props`                  | —                 | Additional configuration passed to Sonner               |

---

### Toast Function API

Imported from the same module:

```tsx
import { toast } from "@/components/Toaster";
```

Common methods:

| Method            | Description           |
| ----------------- | --------------------- |
| `toast()`         | Default toast         |
| `toast.success()` | Success message       |
| `toast.error()`   | Error message         |
| `toast.info()`    | Informational message |
| `toast.warning()` | Warning message       |

Each method accepts:

* `message: string`
* `options?: object` (e.g., action, duration, description)

---

### Example

```tsx id="toast8"
import { Toaster, toast } from "@/components/Toaster";

function ToasterExample() {
  return (
    <div className="p-4">
      <Toaster />

      <button
        onClick={() => toast.success("Profile updated")}
      >
        Update Profile
      </button>

      <button
        onClick={() =>
          toast.error("Failed to update profile")
        }
      >
        Trigger Error
      </button>
    </div>
  );
}
```

```

