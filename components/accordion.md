### Accordion

**Purpose**: Organize content into collapsible sections, allowing users to expand or collapse panels to reveal or hide information. Semantically, it represents a list of items where each item has a header and associated content, improving content hierarchy and reducing clutter on the page.

**Structure**: Use `AccordionRoot` as the container, wrap each section in `AccordionItem`, use `AccordionTrigger` for the clickable header, and `AccordionContent` for the expandable body. Commonly integrated with forms, FAQs, settings panels, or navigation menus. Often used alongside buttons, inputs, or other UI elements within the content areas.

**Usage Notes**:
- Add padding around the accordion for better spacing; it does not include its own margins.
- Use icons like Plus/Minus in triggers for visual cues, but avoid overloading with additional icons.
- Ensure accessibility: Triggers should be keyboard navigable and announce state changes.
- Do not nest accordions deeply; limit to one level for clarity.
- Correct: Use for progressive disclosure in long forms. Incorrect: Use for simple lists without expandable content.

**AccordionRoot Props**:
- All props from `@radix-ui/react-accordion.Root`, such as `type` (single/multiple), `defaultValue`, `value`, `onValueChange`, `disabled`.

**AccordionItem Props**:
- All props from `@radix-ui/react-accordion.Item`, such as `value` (unique ID), `disabled`.

**AccordionTrigger Props**:
- All props from `@radix-ui/react-accordion.Trigger`, plus custom `onClick` handler.
- `children`: ReactNode (header content).
- `className`: String for additional styling.

**AccordionContent Props**:
- All props from `@radix-ui/react-accordion.Content`.
- `children`: ReactNode (expandable content).
- `className`: String for additional styling.

**Example**:
```typescript
import { AccordionRoot, AccordionItem, AccordionTrigger, AccordionContent } from "@/components/Accordion";

function AccordionExample() {
  return (
    <AccordionRoot type="single" collapsible>
      <AccordionItem value="item-1">
        <AccordionTrigger>Section 1</AccordionTrigger>
        <AccordionContent>
          Content for section 1.
        </AccordionContent>
      </AccordionItem>
      <AccordionItem value="item-2">
        <AccordionTrigger>Section 2</AccordionTrigger>
        <AccordionContent>
          Content for section 2.
        </AccordionContent>
      </AccordionItem>
    </AccordionRoot>
  );
}
```