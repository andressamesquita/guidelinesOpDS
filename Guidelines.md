<!--este arquivo contém o conjunto inicial de regras/diretrizes que o Figma Make sempre analisa primeiro-->

# Opala DS Guidelines

This project has access to a custom Design System called **Opala DS**, installed via an npm package. Files in the `guidelines` directory explain how to properly use Opala components, tokens, and patterns.

Always read:
- All files with a name that starts with `overview-`
- All files in the `design-tokens/` folder

Read the files in the `guidelines/components` directory when you want to use a specific component. For example, if you want to use `Toast`, read `guidelines/components/toast.md`. Additional context can be found by inspecting the component implementation in `/node_modules/` if needed.

---

## Component Usage Guidelines — READ THIS FIRST

IMPORTANT: Always prefer using components from **Opala DS** (`@/components`) whenever available.  
Do NOT recreate components that already exist in the design system.

---

## Required Workflow (Follow in Order)

### Step 1: Read Overview Files (REQUIRED)

Read **ALL** files that start with `overview-` in the `guidelines` directory:


- `overview-components.md`
- `overview-icons.md`
- (Any other `overview-*.md` files)

These files define global rules, available components, and system-wide patterns.

---

### Step 2: Read Design Tokens (REQUIRED)

Read **ALL** files inside the `design-tokens/` folder.

This includes (but is not limited to):
- Colors
- Typography
- Spacing
- Border radius
- Shadows

IMPORTANT:  
Do NOT hardcode styles. Always rely on design tokens defined by Opala DS.

---

### Step 3: Plan Components (REQUIRED)

Before writing any code:

- Identify which Opala components are needed
- Prefer composition of existing components instead of creating new ones
- Ensure the chosen components match the intended UX pattern

---

### Step 4: Read Component Guidelines BEFORE Using (REQUIRED)

Before using **ANY** component, you MUST read its specific guideline file:

Examples:
- Using `Button` → Read `guidelines/components/button.md`
- Using `Tooltip` → Read `guidelines/components/tooltip.md`
- Using `TextField` → Read `guidelines/components/textfield.md`

These files include:
- Usage rules
- Props and API
- Do’s and Don’ts
- Accessibility considerations

IMPORTANT:  
Do NOT use a component without reading its documentation first.

---

### Step 5: Plan Icon Usage (REQUIRED)

Before using **ANY** icon:

- Verify that the icon exists in the Opala DS icon system (Lucide-based)
- Use only valid `IconName` values
- If the icon does not exist, choose an alternative and validate it

IMPORTANT:  
Invalid icons will fallback to a default icon and may break UX consistency.

---

## Additional Rules

- Do NOT override component styles using `className`
- Avoid custom styling unless strictly necessary
- When needed, prefer using `style` prop instead of breaking component patterns
- Follow the intended usage of each component (do not repurpose components incorrectly)

---

## Summary

To ensure consistency and quality:

1. Read all overview files  
2. Read all design tokens  
3. Plan component usage  
4. Read component-specific guidelines  
5. Validate icon usage  

Only after completing these steps should you start writing code.
```
