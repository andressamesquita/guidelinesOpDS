# Opala Design System - Guidelines

This project has access to the **Opala Design System** - a comprehensive React component library with carefully designed components, tokens, and patterns. The guidelines directory contains essential information for using this design system effectively.

## Reading Order (CRITICAL - Follow This Order)

Always read the guideline files in this specific order. Skipping steps can lead to incorrect implementations:

### Step 1: Read All Overview Files (REQUIRED)
Read **ALL files** that start with "overview-" in the guidelines directory:

- **overview-components.md** - Complete list of all available components with descriptions and use cases
- **overview-icons.md** - Icon library reference and usage patterns
- **overview-colors.md** - Color system, tokens, and theming guidelines
- **overview-tokens.md** - Design tokens for spacing, typography, shadows, and more

*Do NOT skip any overview files - they provide essential context.*

### Step 2: Read Design Tokens Reference (REQUIRED)
Read **ALL files** in the `design-tokens/` folder:

- Spacing tokens
- Typography tokens  
- Color tokens
- Shadow tokens
- Border radius tokens
- Any other token files

*Design tokens define the visual foundation - you must understand them before writing code.*

### Step 3: Plan What Components You Need
Based on the requirements, identify which components from the Opala Design System you'll use. Refer to the component list in `overview-components.md`.

### Step 4: Read Component-Specific Guidelines (REQUIRED)
**BEFORE using ANY component**, you MUST read its guidelines file first:

- Using **Button**? → Read `guidelines/components/button.md` FIRST
- Using **TextField**? → Read `guidelines/components/textfield.md` FIRST  
- Using **Select**? → Read `guidelines/components/select.md` FIRST
- Using **Alert**? → Read `guidelines/components/alert.md` FIRST
- Using **Dialog**? → Read `guidelines/components/dialog.md` FIRST
- Using **Drawer**? → Read `guidelines/components/drawer.md` FIRST
- Using **Toast**? → Read `guidelines/components/toast.md` FIRST

*Each component has specific props, patterns, and best practices documented in its guidelines file.*

### Step 5: Verify Icons Exist (REQUIRED)
Before using any icon:

1. Check `overview-icons.md` for available icons
2. Verify the icon exists in the icon library
3. Use the correct icon name format (e.g., Icon24Plus, Icon16Warning)
4. If an icon doesn't exist, choose a different one and verify it exists

---

## Important Rules - READ CAREFULLY

### ✅ DO THIS:
1. **Always prefer Opala components** - Use components from the design system instead of creating custom components
2. **Read guidelines first** - Never use a component without reading its guidelines file
3. **Use design tokens** - Reference spacing, colors, and typography from design-tokens
4. **Follow conventions** - Use consistent naming, sizing, and spacing patterns
5. **Verify icons exist** - Check the icon library before using any icon
6. **Use controlled components** - Manage component state from the parent when appropriate
7. **Leverage variant props** - Use variant and color props instead of custom CSS

### ❌ DON'T DO THIS:
1. **Don't skip overview files** - They provide critical context for the entire system
2. **Don't use components without reading their guidelines** - Each component has specific requirements
3. **Don't override component CSS** - Use variant and color props instead
4. **Don't assume icons exist** - Verify them in the icon library first
5. **Don't create custom components** - Use Opala components unless they don't exist
6. **Don't ignore design tokens** - Always use token values for consistency
7. **Don't modify component structure** - Use props for customization, not CSS

---

## Component Organization

The Opala Design System includes:

### Form Components
- TextField - Single-line text input
- Textarea - Multi-line text input
- NumberField - Numeric input with increment/decrement
- SearchField - Search input with microphone support
- Select - Dropdown selection
- SelectMultiple - Multi-select dropdown
- Checkbox - Multi-select checkbox
- RadioButton - Single-select radio button
- Combobox - Searchable dropdown input

### Layout & Structure
- Card - Content container
- Alert - Status notification
- Dialog - Modal dialog
- Drawer - Side navigation panel
- Stepper - Step progression indicator
- Tabs - Tabbed content
- Pagination - Page navigation
- List - Organized item list
- Table - Data table
- Separator - Visual divider

### Navigation
- Button - Primary interactive button
- Breadcrumb - Navigation path
- TopBar - Header navigation
- BottomNavigation - Mobile navigation
- Dropdown - Menu dropdown

### Visual Elements
- Badge - Status label
- Avatar - User profile image
- Chip - Compact tag element
- Icon - SVG icon component
- Image - Responsive image
- Label - Form label
- HelperText - Supporting text
- Tooltip - Contextual help

### Feedback & Indicators
- Toaster - Toast notification system
- LoadingBar - Progress indicator
- ProgressBar - Task progress
- Carousel - Image slider

### Specialized
- ActionSheet - Bottom action panel
- Accordion - Collapsible sections
- Switch - Toggle control
- LoginGovButton - Government auth button
- Header - Page header
- Footer - Page footer

---

## Design Token Categories

All visual properties should use tokens from the design-tokens folder:

### Colors
- Primary colors
- Status colors (Success, Warning, Critical, Info)
- Neutral colors (Backgrounds, Borders, Text)
- Light and dark variants

### Spacing
- Margin and padding values
- Gap spacing for layouts

### Typography
- Font families
- Font sizes
- Font weights
- Line heights

### Shadows
- Elevation levels
- Shadow definitions

### Border Radius
- Component border radius values

### Other Tokens
- Transitions and animations
- Z-index scales
- Opacities

---

## File Structure Reference

```
guidelines/
├── overview-components.md      ← Start here for component overview
├── overview-icons.md           ← Icon library reference
├── overview-colors.md          ← Color system
├── overview-tokens.md          ← All design tokens
├── design-tokens/              ← Token definitions (READ ALL FILES)
│   ├── colors.json
│   ├── spacing.json
│   ├── typography.json
│   ├── shadows.json
│   └── ...
└── components/                 ← Component-specific guidelines
    ├── button.md
    ├── textfield.md
    ├── select.md
    ├── alert.md
    ├── dialog.md
    ├── drawer.md
    ├── toast.md
    └── ...
```

---

## Quick Reference: When to Use Each Component

### Need a Button?
- **Button** - Standard button for actions
- Read: `guidelines/components/button.md`

### Need Text Input?
- **TextField** - Single line → Read `guidelines/components/textfield.md`
- **Textarea** - Multiple lines → Read `guidelines/components/textarea.md`
- **SearchField** - Search input → Read `guidelines/components/searchfield.md`
- **NumberField** - Numbers only → Read `guidelines/components/numberfield.md`

### Need Selection Component?
- **Select** - 4-20 options
- **SelectMultiple** - Multiple selections
- **Checkbox** - Independent options
- **RadioButton** - Mutually exclusive (2-4 options)
- **Combobox** - Searchable with many options

### Need to Show Status/Feedback?
- **Alert** - Persistent message
- **Toaster** - Brief notification
- **HelperText** - Form guidance
- **Tooltip** - Hover help
- **Badge** - Status label

### Need Layout/Structure?
- **Card** - Content container
- **Dialog** - Modal interaction
- **Drawer** - Side navigation
- **Tabs** - Tabbed content
- **Stepper** - Multi-step process
- **Accordion** - Collapsible sections

### Need Navigation?
- **Button** - Direct action
- **Breadcrumb** - Current location
- **TopBar** - Header navigation
- **BottomNavigation** - Mobile nav
- **Dropdown** - Menu options
- **Pagination** - Page navigation

---

## Before You Write Code

**CHECKLIST:**

- [ ] Read ALL overview-*.md files
- [ ] Read ALL files in design-tokens/ folder
- [ ] Identified which components you need
- [ ] Read the guidelines file for EACH component before using it
- [ ] Identified which icons you need
- [ ] Verified all icons exist in the icon library
- [ ] Checked design tokens for colors, spacing, typography
- [ ] Planned your implementation following Opala patterns

*Only after completing ALL checklist items should you write code.*

---

## Getting Component Details

Additional implementation details can be found in:

- **Component source code**: `/src/components/[ComponentName]/`
- **Component types**: `/src/components/[ComponentName]/types.ts`
- **Component variants**: `/src/components/[ComponentName]/variants.ts`
- **Component stories**: `/src/stories/[Component].stories.tsx`

Read your component's guidelines first, then reference these files if you need additional details.

---

## Need Help?

If you need to use a component or icon:

1. First check `overview-components.md` or `overview-icons.md`
2. Then read the specific component/icon guidelines file
3. Reference the design tokens for styling consistency
4. If still unclear, check the component source code and stories

Remember: **Guidelines first, code second.**
