### Switch

**Purpose**: Allow users to toggle between two mutually exclusive states (e.g., on/off, enabled/disabled) with immediate effect.

**Semantic Role**:  
Represents a binary control that changes a system setting instantly. Unlike checkboxes, switches are used for actions that take effect immediately without requiring form submission.

---

### When to Use

Use `Switch` when:

- Toggling a setting on or off (e.g., notifications, dark mode)
- Enabling or disabling features in real time
- Representing binary states with immediate feedback

Commonly used with:

- Forms and settings panels
- Preferences screens
- Cards and configuration sections
- Lists of togglable options

---

### Structure

The component is composed of:

- Optional **left label** (context before the switch)
- A **toggle control** (track + thumb)
- Optional **right label** (context after the switch)

Built on top of `@radix-ui/react-switch`, it includes:

- A track (`SwitchPrimitives.Root`)
- A thumb (`SwitchPrimitives.Thumb`)
- State-based styling (`checked` / `unchecked`)
- Optional labels for better clarity

---

### Usage Notes

- Use switches only for **immediate actions**, not for form submission.
- Always provide clear labeling (`leftLabel` and/or `rightLabel`) to describe the state.
- Avoid ambiguous labels like “On/Off” without context.
- Prefer concise, action-oriented labels (e.g., “Enable notifications”).
- Ensure accessibility by keeping labels visible and meaningful.
- Do not use switches for selecting multiple options (use checkboxes instead).

---

### Correct Usage

✅ Basic usage:
```tsx
<Switch />
````

✅ With labels:

```tsx id="sw1"
<Switch leftLabel="Off" rightLabel="On" />
```

✅ In a settings panel:

```tsx id="sw2"
<div className="flex flex-col gap-4">
  <Switch
    leftLabel="Notifications"
    defaultChecked
  />
  <Switch
    leftLabel="Dark mode"
  />
</div>
```

---

### Incorrect Usage

❌ Without context or labels:

```tsx id="sw3"
<Switch />
```

❌ Using for non-immediate actions:

```tsx id="sw4"
// Avoid using switch inside forms that require submission
<form>
  <Switch />
  <button type="submit">Save</button>
</form>
```

❌ Using for multiple selections:

```tsx id="sw5"
// Incorrect: multiple independent options should use checkboxes
<>
  <Switch leftLabel="Option A" />
  <Switch leftLabel="Option B" />
</>
```

❌ Ambiguous labeling:

```tsx id="sw6"
<Switch leftLabel="Yes" rightLabel="No" />
```

---

### API

#### `Switch Props`

Extends: `ComponentPropsWithoutRef<typeof SwitchPrimitives.Root>`

| Prop         | Type              | Default | Description                                                                                  |
| ------------ | ----------------- | ------- | -------------------------------------------------------------------------------------------- |
| `leftLabel`  | `string`          | —       | Label displayed to the left of the switch                                                    |
| `rightLabel` | `string`          | —       | Label displayed to the right of the switch                                                   |
| `className`  | `string`          | —       | Additional CSS classes for customization                                                     |
| `...props`   | `HTML attributes` | —       | Native Radix Switch props (e.g., `checked`, `defaultChecked`, `onCheckedChange`, `disabled`) |

---

### Behavior

* **Checked state**:

  * Background: `bg-opala-success-default`
  * Thumb moves to the right

* **Unchecked state**:

  * Background: `bg-fg-primary-default`
  * Thumb remains on the left

* **Disabled state**:

  * Reduced opacity
  * No interaction allowed

---

### Example

```tsx id="sw7"
import { Switch } from "@/components/Switch";

function SwitchExample() {
  return (
    <div className="flex flex-col gap-6 p-4">
      <Switch
        leftLabel="Notifications"
        defaultChecked
      />

      <Switch
        leftLabel="Light"
        rightLabel="Dark"
      />

      <Switch
        leftLabel="Auto updates"
        disabled
      />
    </div>
  );
}
```

```
