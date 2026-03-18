### Textarea

**Purpose**: Allow users to input and edit multi-line text, such as descriptions, comments, or detailed information.

**Semantic Role**:  
Represents a form field designed for longer, free-form text input. It communicates that the expected input is not constrained to a single line and may contain more complex or structured content.

---

### When to Use

Use `Textarea` when:

- Collecting long-form input (e.g., descriptions, feedback, observations)
- Allowing users to provide detailed information in forms
- Supporting content that may span multiple lines

Commonly used with:

- Form components (e.g., `Input`, `Select`, `Checkbox`)
- Validation and feedback elements (`HelperText`)
- Form layouts (e.g., stacked fields, grouped sections)
- Submit actions (`Button`)

---

### Structure

The component is composed of:

- Optional **label** (above the field)
- A styled `<textarea>` element
- Optional **helper text** (validation or guidance)
- Optional **character counter** (when `maxLength` is defined)

It also includes:

- Variant-based border styling (`default`, `success`, `warning`, `critical`)
- Size variations (`sm`, `md`, `lg`)
- Internal state for character counting

---

### Usage Notes

- Always provide a `label` when used in forms to ensure accessibility.
- Use `helperText` to guide users or display validation messages.
- Use `maxLength` when input length should be constrained.
- Choose `variant` based on validation state:
  - `default`: neutral
  - `success`: valid input
  - `warning`: attention needed
  - `critical`: error state
- Avoid overly large textareas unless necessary; use appropriate `size`.
- Do not rely solely on placeholder text as a label.

---

### Correct Usage

✅ Basic usage:
```tsx
<Textarea label="Description" />
````

✅ With helper text and validation:

```tsx id="tx1"
<Textarea
  label="Feedback"
  helperText="Please provide as much detail as possible"
  variant="default"
/>
```

✅ With character limit:

```tsx id="tx2"
<Textarea
  label="Comment"
  maxLength={200}
  helperText="Maximum 200 characters"
/>
```

✅ With validation state:

```tsx id="tx3"
<Textarea
  label="Observation"
  variant="critical"
  helperText="This field is required"
/>
```

---

### Incorrect Usage

❌ Missing label in forms:

```tsx id="tx4"
<Textarea placeholder="Type here..." />
```

❌ Using as single-line input:

```tsx id="tx5"
<Textarea />
// Should use Input instead
```

❌ No validation feedback when required:

```tsx id="tx6"
<Textarea label="Message" required />
```

❌ Excessive size without need:

```tsx id="tx7"
<Textarea className="h-[500px]" />
```

---

### API

#### `Textarea Props`

Extends: `ComponentProps<"textarea">`

| Prop         | Type                                                | Default     | Description                                                      |
| ------------ | --------------------------------------------------- | ----------- | ---------------------------------------------------------------- |
| `label`      | `string`                                            | —           | Field label displayed above the textarea                         |
| `helperText` | `string`                                            | —           | Helper or validation message below the field                     |
| `variant`    | `"default" \| "success" \| "warning" \| "critical"` | `"default"` | Visual state of the field                                        |
| `size`       | `"sm" \| "md" \| "lg"`                              | `"md"`      | Controls padding and font size                                   |
| `className`  | `string`                                            | —           | Additional CSS classes                                           |
| `maxLength`  | `number`                                            | —           | Maximum number of characters allowed (enables counter)           |
| `onChange`   | `(event: ChangeEvent<HTMLTextAreaElement>) => void` | —           | Change handler                                                   |
| `...props`   | `textarea attributes`                               | —           | Native textarea props (e.g., `placeholder`, `disabled`, `value`) |

---

### Variants

* **default**: Neutral state
* **success**: Valid input feedback
* **warning**: चेतion or intermediate validation
* **critical**: Error or invalid state

---

### Sizes

* **sm**: Compact spacing, small text
* **md**: Default size
* **lg**: Larger text for emphasis or accessibility

---

### Example

```tsx id="tx8"
import { Textarea } from "@/components/Textarea";

function TextareaExample() {
  return (
    <div className="flex flex-col gap-4 p-4 max-w-md">
      <Textarea
        label="Description"
        helperText="Provide a detailed description"
      />

      <Textarea
        label="Feedback"
        maxLength={150}
        helperText="Max 150 characters"
      />

      <Textarea
        label="Error example"
        variant="critical"
        helperText="This field is required"
      />
    </div>
  );
}
```

```
