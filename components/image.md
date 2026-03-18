### Image

**Purpose**: Display responsive images with optional transparency overlays and error handling for visual content in interfaces. Semantically, it represents an image using the img element for accessibility, with alt text support.

**Structure**: Render the `Image` component with src and alt. Commonly integrated with cards, headers, or content areas in layouts. Frequently used alongside text, buttons, or overlays for rich media.

**Usage Notes**:
- Add padding around for better layout; it handles sizing and overlay.
- Use for photos or graphics; provide alt text.
- Correct: Use for banners or thumbnails. Incorrect: Use for icons or decorative elements without alt.
- Ensure responsive design; use transparency for effects.
- Customize size for mobile layouts.

**Image Props**:
- `size`: "mobileScreen" | "mobileHalfContent" | "mobileContainer" (default: "mobileScreen") - Responsive size.
- `transparency`: "none" | "soft" | "medium" (default: "none") - Overlay opacity.
- All ImgHTMLAttributes<HTMLImageElement> props (e.g., src, alt).

**Example**:
```typescript
import { Image } from "@/components/Image";

function ImageExample() {
  return (
    <Image
      src="image.jpg"
      alt="Description"
      size="mobileScreen"
      transparency="soft"
    />
  );
}
```