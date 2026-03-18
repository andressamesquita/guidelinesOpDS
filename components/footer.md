### Footer

**Purpose**: Display footer content at the bottom of pages, including links, copyright, and additional information with responsive layout. Semantically, it represents a footer using role="contentinfo" for accessibility, providing site-wide information.

**Structure**: Render the `Footer` component with children for main content, and optional bottom sections. Use `FooterColumn` for organizing content. Commonly integrated with headers, content areas, or navigation in page layouts. Frequently used alongside separators or links for site structure.

**Usage Notes**:
- Position at the bottom of the page; it includes padding and separator.
- Use for links, copyright, contact; keep concise.
- Correct: Use for site footer with columns. Incorrect: Use for page headers or main content.
- Ensure responsive design; customize bottom content.
- Integrate with routing for links.

**Footer Props**:
- `children`: ReactNode - Main footer content (e.g., columns).
- `centerBottomContent`: ReactNode - Center bottom section.
- `rightBottomContent`: ReactNode - Right bottom section.
- `className`: String - Additional styles.
- `auxiliarText`: String - Left bottom text.
- All HTMLAttributes<HTMLElement> props.

**FooterColumn Props**:
- `className`: String - Additional styles.
- `children`: ReactNode - Column content.

**Example**:
```typescript
import { Footer, FooterColumn } from "@/components/Footer";

function FooterExample() {
  return (
    <Footer
      auxiliarText="© 2023 Company"
      centerBottomContent={<div>Terms</div>}
      rightBottomContent={<div>Contact</div>}
    >
      <FooterColumn>
        <h4>About</h4>
        <p>Info</p>
      </FooterColumn>
    </Footer>
  );
}
```