# Color Design Tokens

## Naming Pattern

Opala DS uses semantic color tokens following this pattern: `{group}-{category}-{subcategory}-{variant}`
'group' is required (e.g., `fg` for foreground, `opala` for brand); the remaining parts are optional. For instance, `fg-primary-default` has group, category, and variant.

Use borders or background colors to separate sections.

### Quick Decision Tree to Find a Token

**Need a text color?**  
→ Start with `fg-`  
→ Add category like `primary`, `success`  
→ Use `-inverse` for light backgrounds  

**Need a background color?**  
→ Start with `opala-`  
→ Add category like `primary`, `surface`  
→ Use `-hover` or `-selected` for interactions  

**Need an icon or border color?**  
→ Usually matches text color  
→ Same rules apply for contrast  

**Need a brand-specific color?**  
→ Use `opala-` for primary, success, etc.  

## Categories

*   **fg**: Foreground colors for text, icons, and borders (e.g., `fg-strong-default`)
*   **opala**: Brand-specific colors for backgrounds, buttons, and surfaces (e.g., `opala-primary-default`)

## Roles

### Semantic/Status Roles

These communicate specific meanings in the UI:
- **`primary`** - Main brand color (blue)  
  - Use for: Primary buttons, links, key elements  
  - Example: `opala-primary-default`, `fg-primary-default`
- **`success`** - Positive states (green)  
  - Use for: Confirmations, success messages  
  - Example: `opala-success-default`, `fg-success-default`
- **`critical`** - Errors, warnings (red)  
  - Use for: Error alerts, destructive actions  
  - Example: `opala-critical-default`, `fg-critical-default`
- **`warning`** - Cautions (yellow)  
  - Use for: Warnings, alerts  
  - Example: `opala-warning-default`, `fg-warning-default`
- **`selected`** - Selection states (grey)  
  - Use for: Active items, selections  
  - Example: `fg-selected-default`

### "Inverse" Roles

Content for text/icons on light or dark backgrounds:
- **`inverse`** - For contrasting backgrounds (e.g., light text on dark bg)  
  - Use for: Text on dark surfaces  
  - Example: `fg-primary-inverse`

### Data Visualization Roles

For charts and data:
- **`dataviz1-10`** - Color palette for data series  
  - Use for: Graphs, charts, categorical data  
  - Example: `fg-dataviz1-default`, `fg-dataviz1-inverse`

### UI Context Roles

- **`strong`** - High emphasis (e.g., headings)  
  - Use for: Bold text, strong elements  
  - Example: `fg-strong-default`
- **`moderate`** - Medium emphasis  
  - Use for: Body text  
  - Example: `fg-moderate-default`
- **`muted`** - Low emphasis  
  - Use for: Subtle text, disabled states  
  - Example: `fg-muted-default`
- **`surface`** - Background surfaces  
  - Use for: Containers, panels  
  - Example: `opala-surface-moderate-enabled`
- **`light`** - Light variants  
  - Use for: Subtle backgrounds  
  - Example: `opala-light-surface-main-default`

## Prominence

- **`default`** - Standard prominence  
- **`enabled`** - Active state  
- **`hover`** - Hover state  
- **`selected`** - Selected state  
- **`focus`** - Focus state  

## Interaction States

- **`hover`** - Hover interactions  
- **`selected`** - Selected/active states  

## Background Colors

### Creating Hierarchy

**opala-primary-default**  
Default brand background.  

**opala-surface-moderate-enabled**  
Secondary background for containers.  

**opala-light-surface-main-default**  
Tertiary background for nested elements.  

### Common Interaction States

**opala-primary-hover**  
Hover state for brand elements.  

**opala-primary-selected**  
Selected state for brand elements.  

**fg-muted-enabled**  
Disabled text color.  

### Common Hues

**opala-primary**  
Blue for primary actions.  

**opala-success**  
Green for positives.  

**opala-critical**  
Red for errors.  

**opala-warning**  
Yellow for cautions.  

**opala-strong**  
Light blue for strong emphasis.  

### Tertiary Backgrounds

Light tints like `opala-light-background-primary-hover` for subtle fills.  

### Special UI Elements

**opala-light-surface-main**  
Main light surfaces.  

**opala-light-background**  
Background variants for hover states.  

## Examples of Token Usage

```css
/* Primary button */
.primaryButton {
  background: var(--opala-primary-default);
  color: var(--fg-primary-inverse);
}

/* Success banner */
.successBanner {
  background: var(--opala-success-default);
  color: var(--fg-success-inverse);
}

/* Disabled text */
.disabledText {
  color: var(--fg-muted-enabled);
}
```

**Rule:** Use `inverse` for text on brand-colored backgrounds for contrast. For light backgrounds, use default fg colors. Combine fg and opala tokens for hierarchy.