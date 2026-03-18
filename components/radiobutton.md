### RadioButton

**Purpose**: Allow users to select a single option from a predefined set of mutually exclusive choices.

**Semantic Role**:  
Represents a single selectable option within a group where only one value can be selected at a time. It is typically used in forms to enforce exclusive selection.

---

### When to Use

Use `RadioButton` when:

- Users must choose **only one option** from a list
- All available options should be visible at once
- You want to provide clear, comparable choices

Commonly used with:

- Form groups (e.g., preferences, settings, filters)
- Fieldsets or selection sections
- Validation systems (with helper or error messages)
- Components like `HelperText`, form labels, and containers

---

### Structure

The component is composed of:

- A native `<input type="radio">`
- A clickable **label** associated via `htmlFor`
- Optional **description** for additional context
- Optional **helper text** for validation or guidance
- Variant and size-based styling

---

### Usage Notes

- Always group radio buttons using the same `name` attribute to ensure exclusive selection.
- Provide a clear `label` for each option.
- Use `description` when additional explanation is needed.
- Use `helperText` for validation feedback or instructions.
- Ensure the `id` is unique and matches the label’s `htmlFor`.
- Prefer radio buttons over dropdowns when there are **few options (2–5)**.

---

### Correct Usage

✅ Basic grouped usage:
```tsx
<>
  <RadioButton name="plan" id="basic" label="Basic Plan" />
  <RadioButton name="plan" id="premium" label="Premium Plan" />
</>
````

✅ With description and helper text:

```tsx id="7n3k2v"
<RadioButton
  name="notification"
  id="email"
  label="Email"
  description="Receive updates via email"
  helperText="Recommended option"
/>
```

✅ With variants and sizes:

```tsx id="3f9k1q"
<RadioButton
  name="status"
  id="active"
  label="Active"
  variant="success"
  size="lg"
/>
```

---

### Incorrect Usage

❌ Using radio button for multiple selections:

```tsx id="g2l9md"
<RadioButton name="features" label="Option A" />
<RadioButton name="features" label="Option B" />
// Should be checkbox instead
```

❌ Missing shared `name` (breaks grouping):

```tsx id="k8s4wd"
<RadioButton id="opt1" label="Option 1" />
<RadioButton id="opt2" label="Option 2" />
```

❌ Missing label (accessibility issue):

```tsx id="z1x8cv"
<RadioButton name="plan" id="basic" />
```

❌ Overloading with too many options:

```tsx id="p0q9rs"
{/* Avoid large lists — consider Select instead */}
```

---

### API

#### `RadioButton Props`

Extends: `ComponentPropsWithoutRef<"input">` (excluding `size`)

| Prop          | Type                                             | Default  | Description                                                  |
| ------------- | ------------------------------------------------ | -------- | ------------------------------------------------------------ |
| `id`          | `string`                                         | —        | Unique identifier for the input and label association        |
| `name`        | `string`                                         | —        | Groups radio buttons (required for exclusive selection)      |
| `label`       | `string`                                         | —        | Main label displayed next to the radio                       |
| `description` | `string`                                         | —        | Additional descriptive text below the label                  |
| `helperText`  | `string`                                         | —        | Helper or validation message displayed below                 |
| `variant`     | `"info" \| "warning" \| "critical" \| "success"` | `"info"` | Visual style and semantic meaning                            |
| `size`        | `"sm" \| "md" \| "lg"`                           | `"md"`   | Controls the size of the radio and text                      |
| `className`   | `string`                                         | —        | Additional CSS classes                                       |
| `...props`    | `input attributes`                               | —        | Native input props (`checked`, `onChange`, `disabled`, etc.) |

---

### Variants

* **info**: Default neutral state
* **success**: Positive or confirmed option
* **warning**: Requires attention
* **critical**: Error or destructive context

---

### Sizes

* **sm**: Compact layout (dense forms)
* **md**: Default size
* **lg**: Emphasized or touch-friendly interfaces

---

### Example

```tsx id="m4t8zn"
import { RadioButton } from "@/components/RadioButton";

function RadioExample() {
  return (
    <div className="flex flex-col gap-3">
      <RadioButton
        name="plan"
        id="basic"
        label="Basic Plan"
        description="Essential features"
      />
      <RadioButton
        name="plan"
        id="pro"
        label="Pro Plan"
        description="Advanced features"
        variant="success"
      />
      <RadioButton
        name="plan"
        id="enterprise"
        label="Enterprise"
        description="Full access"
        helperText="Contact sales for details"
        variant="warning"
      />
    </div>
  );
}
```

```
