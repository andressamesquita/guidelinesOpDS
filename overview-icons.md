<!--
Este arquivo apresenta o Figma Make a aspectos específicos do sistema de design: aqui ele explica quais ÍCONES estão disponíveis e quaisquer padrões de uso comuns que se apliquem a todos os componentes.
-->

### Icon Library

Opala DS provides a flexible icon system based on the **Lucide icon set**, exposed through a single `Icon` component.

All icons are dynamically resolved using the `name` prop and must exist in the `lucide-react` `icons` registry.

---

### Available Icons

- Icons are sourced from the **Lucide icon library**
- All available icons are accessible via:
```ts
  import { icons } from "lucide-react"
````

* The `IconName` type ensures only valid icon names are used:

```ts
  export type IconName = keyof typeof icons
```

IMPORTANT: Always verify that the icon exists in the Lucide library before using it. Invalid names will fallback to a default icon.

---

### Usage Pattern

```typescript
import { Icon } from "@/components/Icon";

// Basic usage
<Icon name="ArrowRight" />

// With custom size and color
<Icon name="Check" size={20} color="green" />

// Inside components
<Button>
  <Icon name="Plus" />
  Add item
</Button>
```

---

### Props

| Prop           | Type          | Default | Description                             |
| -------------- | ------------- | ------- | --------------------------------------- |
| `name`         | `IconName`    | —       | Name of the icon (must exist in Lucide) |
| `size`         | `number`      | `24`    | Icon size in pixels                     |
| `color`        | `string`      | —       | Icon color                              |
| `...restProps` | `LucideProps` | —       | Additional props passed to the icon     |

---

### Behavior

* If `name` is not provided → renders a default `BadgeInfo` icon
* If `name` is invalid → renders a fallback `BadgeInfo` icon
* Icons are rendered as React components dynamically

---

### Best Practices

* Always use the `Icon` component instead of importing icons directly
* Keep icon usage consistent across the interface
* Use icons to support meaning, not replace text
* Prefer default sizing (`24px`) unless context requires otherwise
* Ensure icons are visually aligned with surrounding elements

---

### Do's and Don'ts

✅ Correct usage:

```tsx
<Icon name="ArrowRight" />
<Icon name="CheckCircle" color="green" />
```

❌ Avoid invalid icon names:

```tsx
<Icon name="NonExistentIcon" />
```

❌ Avoid using icons without semantic meaning:

```tsx
<Icon name="Star" /> // without context
```

❌ Avoid inconsistent sizing:

```tsx
<Icon name="User" size={13} />
```

---

### Notes

* Icon names follow **PascalCase** (e.g., `"ArrowRight"`, `"CheckCircle"`)
* All icons come from `lucide-react`, so refer to its documentation or source for the full list
* Do not modify internal SVG properties (e.g., stroke width), as it may break visual consistency

```
```
