<!--
Este arquivo apresenta o Figma Make a aspectos específicos do sistema de design: aqui ele explica quais COMPONENTES estão disponíveis e quaisquer padrões de uso comuns que se apliquem a todos os componentes.
-->

<!--REFAZEEEEERRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRRR-->

## Components

Always prefer components from the Opala DS package (imported from @/components) if they are available. Each component has a guidelines file that contains helpful examples and additional context for you to use. You must follow all relevant instructions.

Here are the guidelines files and additional guidelines for the Opala DS components:

| Component | Overview | Guidelines file |
|----------|----------|----------|
| Accordion | Collapsible UI element with title, content, icon, and variants | [accordion.md](components/accordion.md) |
| ActionSheet | Mobile-friendly bottom action panel for grouped actions | [actionsheet.md](components/actionsheet.md) |
| Alert | Feedback message for status, warnings, or errors | [alert.md](components/alert.md) |
| Avatar | Visual representation of a user or entity | [avatar.md](components/avatar.md) |
| Badge | Small status or count indicator | [badge.md](components/badge.md) |
| BottomNavigation | Navigation bar fixed at the bottom of the screen | [bottomnavigation.md](components/bottomNavigation.md) |
| Breadcrumb | Navigation aid showing hierarchy and path | [breadcrumb.md](components/breadcrumb.md) |
| Button | Primary interactive element for actions | [button.md](components/button.md) |
| Card | Container for grouping related content | [card.md](components/card.md) |
| Carousel | Horizontal scrollable content container | [carousel.md](components/carousel.md) |
| Checkbox | Input control for multiple selections | [checkbox.md](components/checkbox.md) |
| Chip | Compact element representing input, attribute, or action | [chip.md](components/chip.md) |
| Combobox | Input field with autocomplete and suggestions | [combobox.md](components/combobox.md) |
| Dialog | Modal window for focused tasks or information | [dialog.md](components/dialog.md) |
| Drawer | Slide-in panel from screen edge | [drawer.md](components/drawer.md) |
| Dropdown | Expandable menu for actions or selection | [dropdown.md](components/dropdown.md) |
| Footer | Bottom section of the layout | [footer.md](components/footer.md) |
| Header | Top section of the layout | [header.md](components/header.md) |
| HelperText | Supporting text for inputs or UI elements | [helpertext.md](components/helperText.md) |
| Image | Component for displaying images with styling | [image.md](components/image.md) |
| List | Structured collection of items | [list.md](components/list.md) |
| LoadingBar | Visual indicator of loading progress | [loadingbar.md](components/loadingBar.md) |
| LoginGovButton | Gov.br authentication call-to-action button | [logingovbutton.md](components/logingovbutton.md) |
| NumberField | Numeric input field | [numberfield.md](components/numberfield.md) |
| Pagination | Navigation between pages of content | [pagination.md](components/pagination.md) |
| ProgressBar | Visual indicator of task progress | [progressbar.md](components/progressbar.md) |
| RadioButton | Input control for single selection | [radiobutton.md](components/radiobutton.md) |
| SearchField | Input field for search queries | [searchfield.md](components/searchfield.md) |
| Select | Dropdown selection input | [select.md](components/select.md) |
| SelectMultiple | Multi-select input component | [selectmultiple.md](components/selectMultiple.md) |
| Separator | Visual divider between content sections | [separator.md](components/separator.md) |
| Stepper | Step-by-step progress indicator | [stepper.md](components/stepper.md) |
| Switch | Toggle input for binary states | [switch.md](components/switch.md) |
| Table | Structured data display in rows and columns | [table.md](components/table.md) |
| Tabs | Organize content into tabbed sections | [tabs.md](components/tabs.md) |
| TextField | Standard text input field | [textfield.md](components/textfield.md) |
| Textarea | Multi-line text input field | [textarea.md](components/textarea.md) |
| Toast | Temporary notification message | [toast.md](components/toast.md) |
| Tooltip | Contextual helper displayed on hover/focus | [tooltip.md](components/tooltip.md) |
| TopBar | Top navigation and action bar | [topbar.md](components/topbar.md) |

IMPORTANT: Do not specify a className property on any Opala DS components, as this will break the component. You should avoid overriding styling. Where strictly necessary (e.g., a button background color), use a style object property.

## General Component Usage and Best Practices

### Common Props

Most Opala DS components accept these common props:
- `title`: String for the header text
- `children`: Content to display when expanded
- `icon`: String for the icon type (e.g., "ArrowUp")
- `variant`: String for styling variant (e.g., "default", "ghost")
- `disabled`: Boolean to disable the component
- Components always extend the types of their base element, e.g., Accordion accepts all div-related props

### Controlled vs Uncontrolled

- **Controlled**: Component receives `title`, `children`, and event handlers, parent manages state
- **Uncontrolled**: Component manages own expansion state, use default props for initial setup
- Prefer controlled for most cases in modern React

### Sizing

- Accordion supports fixed width containers (e.g., w-96 for 384px)
- Adjust container size as needed for layout

### Variants

- Use "default" for standard styling
- Use "ghost" for minimal styling
- Apply "disabled" for non-interactive states

### Icon Usage

- Icons are specified as strings (e.g., "ArrowUp")
- Ensure icons exist in the design system before use
- Icons are displayed in the header for visual cues

```````md title="guidelines/overview-icons.md"
### Icon Library

Opala DS provides a set of icons for components. All icons are React components imported from the design system.

IMPORTANT: Always check the available icons in the design system to confirm existence before using.
**Icon Sizes**:

- Icons are typically 24px for headers and UI elements

**Usage Pattern**:

```typescript
import { Accordion } from "@/components/Accordion/index";

// In components
<Accordion icon="ArrowUp" title="Example" />
```

- Specify icons via the `icon` prop as a string
- Never modify icon properties directly as this may break styling

**Finding Icons**:

- Icon names are PascalCase strings (e.g., "ArrowUp")
- Check component props for supported icon options
```