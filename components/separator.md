### Separator

**Purpose**: Visually divide and organize content into distinct sections, improving readability and layout structure.

**Semantic Role**:  
Represents a thematic or visual separation between groups of content. It can be purely decorative or semantic depending on context (e.g., separating sections vs. structuring accessible regions).

---

### When to Use

Use `Separator` when:

- Dividing sections within layouts (e.g., forms, cards, panels)
- Separating groups of actions (e.g., buttons, menu items)
- Structuring content in lists or dashboards
- Improving visual hierarchy without adding extra spacing alone

Commonly used with:

- Cards and containers
- Forms and input groups
- Navigation menus and dropdowns
- Modals and side panels
- Lists and data displays

---

### Structure

The component is based on `@radix-ui/react-separator` and renders:

- A `div`-like element with semantic support
- Orientation-based layout:
  - Horizontal (`width: 100%`, `height: 1px`)
  - Vertical (`height: 100%`, `width: 1px`)
- A background color (`bg-border`) representing the divider

---

### Usage Notes

- Use **horizontal separators** to divide vertical content sections.
- Use **vertical separators** to divide horizontal layouts (e.g., inline actions).
- Prefer spacing first; use separators only when visual distinction is necessary.
- Use `decorative={true}` when the separator is purely visual (default).
- Use `decorative={false}` when the separator conveys semantic meaning for assistive technologies.
- Avoid overusing separators, as it can clutter the interface.

---

### Correct Usage

✅ Basic horizontal separator:
```tsx
<Separator />
````

✅ Separating sections inside a card:

```tsx id="sep1"
<Card>
  <SectionA />
  <Separator />
  <SectionB />
</Card>
```

✅ Vertical separator between inline elements:

```tsx id="sep2"
<div className="flex items-center gap-2">
  <Button>Save</Button>
  <Separator orientation="vertical" />
  <Button>Cancel</Button>
</div>
```

---

### Incorrect Usage

❌ Using separator instead of spacing:

```tsx id="sep3"
<>
  <Text />
  <Separator />
  <Text />
</>
```

❌ Overusing separators:

```tsx id="sep4"
<>
  <Separator />
  <Separator />
  <Separator />
</>
```

❌ Incorrect orientation usage:

```tsx id="sep5"
// Vertical separator in vertical layout without height constraint
<Separator orientation="vertical" />
```

❌ Using as a decorative element without purpose:

```tsx id="sep6"
<div>
  <Separator />
</div>
```

---

### API

#### `Separator Props`

Extends: `React.ComponentPropsWithoutRef<typeof SeparatorPrimitive.Root>`

| Prop          | Type                         | Default        | Description                                            |
| ------------- | ---------------------------- | -------------- | ------------------------------------------------------ |
| `orientation` | `"horizontal" \| "vertical"` | `"horizontal"` | Defines the direction of the separator                 |
| `decorative`  | `boolean`                    | `true`         | Whether the separator is purely decorative or semantic |
| `className`   | `string`                     | —              | Additional CSS classes for customization               |
| `...props`    | `HTML attributes`            | —              | Native props passed to the root element                |

---

### Variants / Behavior

* **horizontal**:

  * Full width (`w-full`)
  * Height of `1px`
  * Used to separate stacked content

* **vertical**:

  * Full height (`h-full`)
  * Width of `1px`
  * Used to separate inline elements

---

### Example

```tsx id="sep7"
import { Separator } from "@/components/Separator";

function SeparatorExample() {
  return (
    <div className="flex flex-col gap-4 p-4">
      <div>Section 1</div>
      <Separator />
      <div>Section 2</div>

      <div className="flex items-center gap-2">
        <span>Option A</span>
        <Separator orientation="vertical" />
        <span>Option B</span>
      </div>
    </div>
  );
}
```

```
