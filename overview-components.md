# Components Overview - Opala Design System

Always prefer components from the Opala Design System (imported from the main package) when available. Each component has been carefully designed to work together and follow consistent patterns.

## Available Components

| Component | Overview | Use Case |
|-----------|----------|----------|
| Accordion | Expandable section container with collapsible content | Organizing related content into collapsible panels |
| ActionSheet | Bottom sliding panel with action options | Mobile-friendly action menus and bottom toolbars |
| Alert | Status notification with customizable severity | Displaying important messages, warnings, and confirmations |
| Avatar | User profile image with fallback support | Displaying user avatars with status indicators |
| Badge | Small status indicator or label | Highlighting important attributes or statuses |
| BottomNavigation | Navigation bar fixed at bottom of screen | Mobile navigation with icon and label options |
| Breadcrumb | Navigation path indicator | Showing user location in app hierarchy |
| Button | Primary interactive button component | Triggering actions and form submissions |
| Card | Container for grouped content | Organizing related content into distinct sections |
| Carousel | Image/content slider with autoplay support | Displaying multiple items in rotatable carousel |
| Checkbox | Multi-select checkbox input | Enabling multiple selections from options |
| Chip | Compact dismissible tag element | Tags, filters, and inline selections |
| Combobox | Searchable dropdown input | Combining search input with dropdown options |
| Dialog | Modal dialog with overlay | Focused user interactions requiring confirmation |
| Drawer | Side navigation panel | Navigation drawer with expandable/collapsible states |
| Dropdown | Menu dropdown with customizable items | Creating dropdown menus with multiple actions |
| Footer | Page footer component | Displaying footer content and links |
| Header | Page header component | Displaying header content and branding |
| HelperText | Small text descriptions and error messages | Providing guidance and validation feedback |
| Icon | SVG icon component | Rendering single icons inline |
| IconRenderer | Flexible icon rendering utility | Dynamic icon rendering with multiple input types |
| Image | Responsive image component | Displaying images with proper sizing |
| Label | Form label element | Associating text labels with form inputs |
| List | Organized list with multiple variants | Displaying lists of items with various layouts |
| LoadingBar | Progress indicator bar | Showing loading progress state |
| LoginGovButton | Login.gov authentication button | Government authentication integration |
| NumberField | Numeric input with increment/decrement | Entering and adjusting numeric values |
| Pagination | Page navigation control | Navigating between paginated content |
| ProgressBar | Progress indicator for tasks | Showing progress of ongoing operations |
| RadioButton | Single-select radio input | Enabling mutually exclusive selections |
| SearchField | Search input with optional microphone | Searching with voice input capability |
| Select | Dropdown select for predefined options | Selecting single item from list |
| SelectMultiple | Multi-select dropdown component | Selecting multiple items from dropdown |
| Separator | Visual divider line | Breaking up sections visually |
| Stepper | Step progression indicator | Guiding users through multi-step processes |
| Switch | Toggle switch control | Binary on/off selection |
| Table | Data table with rows and columns | Displaying structured tabular data |
| Tabs | Tabbed content container | Organizing content into switchable tabs |
| Textarea | Multi-line text input | Entering longer text content |
| TextField | Single-line text input | Entering short text values |
| Toaster | Toast notification system | Showing temporary notifications |
| Tooltip | Floating informational popover | Providing contextual help and tooltips |
| TopBar | Header navigation bar | Primary top navigation element |

## General Component Usage and Best Practices

### Common Props

Most Opala Design System components accept these common props:

- **`className`**: String for additional CSS classes (use sparingly)
- **`disabled`**: Boolean to disable the component
- **`data-*`**: Data attributes for testing and custom attributes
- **`size`**: Most components support size variants like `"sm"`, `"md"`, `"lg"`
- **`variant`**: Style variants (e.g., `"solid"`, `"outline"`, `"ghost"`)
- **`color`**: Color variants when applicable
- Components extend the types of their base elements (e.g., Button accepts all HTML button props)

### Styling Guidelines

**IMPORTANT**: Be mindful when overriding component styling:

- **Avoid modifying styling** through `className` on FPL components when possible
- Use **variant and color props** for styling changes (preferred approach)
- Use **style object property** for strictly necessary modifications (e.g., custom spacing)
- Component structure and layout are optimized for consistency - changing them may break appearance
- Use `size` props to control component dimensions instead of custom CSS

### Controlled vs Uncontrolled Components

- **Controlled**: Component receives `value` and `onChange` props, parent manages state
  ```tsx
  const [value, setValue] = useState('');
  <TextField value={value} onChange={(e) => setValue(e.target.value)} />
  ```
- **Uncontrolled**: Component manages own state, use `defaultValue` for initial value
  ```tsx
  <TextField defaultValue="initial" />
  ```
- **Best Practice**: Prefer controlled components for modern React applications

### Size Properties

- **Most components**: Support `size` prop with values: `"sm"` (small), `"md"` (medium, default), `"lg"` (large)
- **Input components**: TextField, NumberField, SearchField follow consistent sizing
- **Button**: Available with default sizing; use `size` prop for variations
- **Icons**: Use Icon24 for standard 24px icons, Icon16 for 16px icons

### Form Inputs

- **TextField**: For single-line text input
- **Textarea**: For multi-line text input
- **NumberField**: For numeric input with increment/decrement controls
- **SearchField**: For search input with optional microphone support
- **Select**: For single selection from predefined options (4-20 items)
- **SelectMultiple**: For multiple selections from dropdown
- **Checkbox**: For multiple independent selections
- **RadioButton**: For mutually exclusive selections (2-4 options)
- **Combobox**: For searchable dropdown (alternative to Select)

### Selection Components

- Use **Select** for 4-20 predefined options
- Use **TextField** for freeform values
- Use **RadioButton** for 2-4 mutually exclusive options
- Use **Combobox** for searchable dropdown with many options or dynamic data
- Use **SelectMultiple** for selecting multiple items from a dropdown
- Use **Checkbox** for independent multi-select with visible options

### Layout Components

- **Card**: Group related content into distinct visual blocks
- **Alert**: Display messages with different severity levels (info, warning, critical, success)
- **Drawer**: Side navigation panel with expand/collapse functionality
- **BottomNavigation**: Mobile navigation with icon labels
- **TopBar**: Primary navigation header
- **Separator**: Visual divider between sections
- **List**: Organized list with avatar, title, subtitle, and action options

### Feedback Components

- **Toaster**: Brief notifications that auto-dismiss (use for feedback messages)
- **Alert**: Persistent messages that require acknowledgment (use for status and warnings)
- **HelperText**: Supporting text below form inputs for guidance and errors
- **Tooltip**: Hover-triggered contextual help
- **LoadingBar**: Show progress of ongoing operations
- **ProgressBar**: Display completion progress of tasks

### Navigation Patterns

- **Breadcrumb**: Show current location in hierarchical navigation
- **Tabs**: Switch between related content panels
- **Stepper**: Guide users through sequential steps
- **Pagination**: Navigate between pages of content
- **Drawer**: Side navigation for main app sections
- **TopBar**: Primary navigation header
- **BottomNavigation**: Mobile-friendly navigation (mobile-specific)

## Component Composition and Architecture

### Accessibility

All Opala components are built with accessibility in mind:

- Proper ARIA labels and roles
- Keyboard navigation support
- Focus management
- Semantic HTML structure
- Color-independent information conveyance

### Theme and Color System

The Opala Design System uses a consistent color system:

- **Primary colors**: Used for main actions and emphasis
- **Status colors**: Success (green), Warning (orange), Critical (red), Info (blue)
- **Neutral colors**: For backgrounds, borders, and disabled states
- **Light/Dark variants**: For foreground and background elements

Color variants are typically available through:

- `severity` prop (for alerts, status components)
- `variant` prop (for styling variations)
- `color` prop (for button and interactive components)

### Responsive Design

Components are designed to be responsive:

- Size props adjust for different screen sizes
- Create responsive layouts using size variants
- BottomNavigation and mobile-specific components handle small screens
- TopBar and Drawer adapt to different viewports

## Best Practices Summary

1. **Use variant and color props** for styling instead of `className`
2. **Keep components controlled** when managing state from parent
3. **Use semantic components** (e.g., use Select for dropdowns, not TextField)
4. **Maintain consistent sizing** across related components
5. **Leverage HelperText** for form guidance and error messages
6. **Use Alert for persistent messages**, Toaster for temporary notifications
7. **Follow accessibility patterns** - all components support ARIA attributes
8. **Test keyboard navigation** - all interactive components are keyboard accessible
9. **Avoid overriding component structure** - use props for customization
10. **Use appropriate size prop** instead of custom CSS for spacing and sizing

## Component Status

All components in the Opala Design System are production-ready and thoroughly tested. Components follow consistent naming conventions and prop patterns for improved developer experience.

For detailed usage examples of any component, refer to the storybook stories files in the `src/stories` directory.
