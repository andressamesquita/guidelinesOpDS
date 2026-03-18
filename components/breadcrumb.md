### Breadcrumb

**Purpose**: Provide navigation context by displaying the hierarchical path to the current page, allowing users to understand their location and navigate back. Semantically, it represents a trail of links using aria-label="breadcrumb" for accessibility, helping users orient themselves in complex sites.

**Structure**: Use `BreadcrumbRoot` as the container, `BreadcrumbList` for the ordered list, `BreadcrumbItem` for each step, `BreadcrumbLink` for navigable items, `BreadcrumbPage` for the current page, and `BreadcrumbSeparator` between items. Commonly integrated with page headers, navigation bars, or content areas. Frequently used alongside headers, footers, or sidebars in web applications.

**Usage Notes**:
- Place at the top of pages for visibility; use separators for clarity.
- Limit to essential paths; use ellipsis for long trails.
- Correct: Use for multi-level sites like e-commerce or docs. Incorrect: Use for single-page apps without hierarchy.
- Ensure links are functional and current page is marked.
- Customize separators (slash or chevron) for branding.

**BreadcrumbRoot Props**:
- All nav props, plus `separator`: ReactNode - Custom separator element.

**BreadcrumbList Props**:
- All ol props.

**BreadcrumbItem Props**:
- All li props, plus `isCurrent`: Boolean - If this is the current page.
- `href`: String - Link URL for non-current items.

**BreadcrumbLink Props**:
- All a props, plus `asChild`: Boolean - Render as child component.

**BreadcrumbPage Props**:
- All span props.

**BreadcrumbSeparator Props**:
- All li props, plus `separatorType`: "slash" | "chevron" (default: "slash") - Icon type.

**BreadcrumbEllipsis Props**:
- All span props - For truncated paths.

**Example**:
```typescript
import { BreadcrumbRoot, BreadcrumbList, BreadcrumbItem, BreadcrumbLink, BreadcrumbPage, BreadcrumbSeparator } from "@/components/Breadcrumb";

function BreadcrumbExample() {
  return (
    <BreadcrumbRoot>
      <BreadcrumbList>
        <BreadcrumbItem>
          <BreadcrumbLink href="/">Home</BreadcrumbLink>
        </BreadcrumbItem>
        <BreadcrumbSeparator />
        <BreadcrumbItem>
          <BreadcrumbLink href="/products">Products</BreadcrumbLink>
        </BreadcrumbItem>
        <BreadcrumbSeparator />
        <BreadcrumbItem isCurrent>
          <BreadcrumbPage>Item Details</BreadcrumbPage>
        </BreadcrumbItem>
      </BreadcrumbList>
    </BreadcrumbRoot>
  );
}
```