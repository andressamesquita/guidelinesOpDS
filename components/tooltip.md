### Tooltip

**Purpose**: Provide contextual, non-intrusive information when users hover, focus, or interact with an element.

**Semantic Role**:  
Represents supplementary information associated with a UI element. Tooltips enhance usability by offering hints, clarifications, or additional details without cluttering the interface.

---

### When to Use

Use `Tooltip` when:

- Providing additional context for icons, buttons, or actions
- Explaining unclear labels or abbreviations
- Offering short helper text without occupying layout space
- Enhancing accessibility with extra descriptive information

Commonly used with:

- Icon buttons (e.g., actions, settings)
- Form inputs (help or validation hints)
- Navigation items
- Data visualization elements
- Disabled actions (to explain why they are unavailable)

---

### Structure

The component is built on top of `@radix-ui/react-tooltip` and includes:

- A **Trigger** element (wrapped via `asChild`)
- A **Content container** with:
  - `title` (required)
  - `description` (optional)
- A directional **arrow**
- Configurable positioning (`side`)

---

### Usage Notes

- Keep tooltip content **short and concise**.
- Always provide a meaningful `title`.
- Use `description` only when additional clarification is necessary.
- Avoid placing interactive elements inside tooltips.
- Do not rely on tooltips as the only way to convey critical information.
- Ensure tooltips are accessible via keyboard (focus states).
- Prefer default delay to avoid flickering on quick hover.

---

### Correct Usage

✅ Basic usage with icon:
```tsx
<Tooltip content={{ title: "Edit item" }}>
  <IconButton icon="Edit" />
</Tooltip>
````

✅ With title and description:

```tsx id="tt1"
<Tooltip
  content={{
    title: "Delete",
    description: "This action cannot be undone"
  }}
>
  <Button variant="destructive">Delete</Button>
</Tooltip>
```

✅ On form input helper:

```tsx id="tt2"
<Tooltip content={{ title: "Password must be at least 8 characters" }}>
  <Input placeholder="Password" />
</Tooltip>
```

---

### Incorrect Usage

❌ Using tooltip for essential information:

```tsx id="tt3"
<Tooltip content={{ title: "You must fill this field to continue" }}>
  <Input />
</Tooltip>
```

❌ Long or complex content:

```tsx id="tt4"
<Tooltip content={{ title: "Very long explanation that should not be inside a tooltip because it becomes hard to read and impacts usability" }}>
  <Button />
</Tooltip>
```

❌ Multiple tooltips in dense areas:

```tsx id="tt5"
<>
  <Tooltip content={{ title: "A" }}><Icon /></Tooltip>
  <Tooltip content={{ title: "B" }}><Icon /></Tooltip>
  <Tooltip content={{ title: "C" }}><Icon /></Tooltip>
</>
```

❌ Wrapping non-interactive or large containers:

```tsx id="tt6"
<Tooltip content={{ title: "Info" }}>
  <div>Entire section</div>
</Tooltip>
```

---

### API

#### `Tooltip Props`

Extends: `ComponentPropsWithoutRef<typeof TooltipPrimitive.Root>`

| Prop                      | Type                                      | Default | Description                               |
| ------------------------- | ----------------------------------------- | ------- | ----------------------------------------- |
| `children`                | `ReactElement`                            | —       | عنصر that triggers the tooltip            |
| `content`                 | `{ title: string; description?: string }` | —       | Tooltip content                           |
| `side`                    | `"top" \| "right" \| "bottom" \| "left"`  | `"top"` | Preferred position of the tooltip         |
| `open`                    | `boolean`                                 | —       | Controlled open state                     |
| `defaultOpen`             | `boolean`                                 | —       | Initial open state (uncontrolled)         |
| `onOpenChange`            | `(open: boolean) => void`                 | —       | Callback when open state changes          |
| `delayDuration`           | `number`                                  | —       | Delay before showing tooltip (ms)         |
| `disableHoverableContent` | `boolean`                                 | —       | Prevents interaction with tooltip content |
| `...props`                | `TooltipPrimitive.Content props`          | —       | Additional props for content container    |

---

### Behavior

* Triggered on **hover** and **focus**
* Positioned relative to the trigger element
* Includes subtle animation based on `side`
* Renders in a portal to avoid layout overflow issues

---

### Example

```tsx id="tt7"
import { Tooltip } from "@/components/Tooltip";
import { Button } from "@/components/Button";

function TooltipExample() {
  return (
    <div className="flex gap-4 p-4">
      <Tooltip content={{ title: "Save changes" }}>
        <Button>Save</Button>
      </Tooltip>

      <Tooltip
        content={{
          title: "Delete item",
          description: "This action cannot be undone"
        }}
        side="bottom"
      >
        <Button variant="destructive">Delete</Button>
      </Tooltip>
    </div>
  );
}
```

```