### Carousel

**Purpose**: Display a series of content items in a scrollable, swipeable container, allowing users to navigate through slides horizontally or vertically. Semantically, it represents a carousel using role="region" and aria-roledescription="carousel" for accessibility, enabling keyboard navigation and screen reader support.

**Structure**: Use `CarouselRoot` as the main container with `useCarousel` hook for context, wrap slides in `CarouselContent` and `CarouselItem`, and add navigation with `CarouselPrevious` and `CarouselNext`. Commonly integrated with images, cards, or testimonials in galleries or product showcases. Frequently used alongside buttons, indicators, or modals for interactive content.

**Usage Notes**:
- Add padding around the carousel for better layout; it handles overflow internally.
- Use for showcasing multiple items like images or features; avoid for single items.
- Correct: Use for image galleries or feature highlights. Incorrect: Use for long lists without navigation.
- Ensure keyboard accessibility with arrow keys; disable buttons when not scrollable.
- Customize orientation for vertical carousels if needed.

**CarouselRoot Props**:
- `opts`: CarouselOptions - Embla carousel options (e.g., loop, align).
- `plugins`: CarouselPlugin - Embla plugins.
- `orientation`: "horizontal" | "vertical" (default: "horizontal") - Scroll direction.
- `setApi`: Function - Callback to set carousel API.
- `className`: String - Additional CSS classes.

**CarouselContent Props**:
- All div props - Container for slides.

**CarouselItem Props**:
- All div props - Individual slide wrapper.

**CarouselPrevious Props**:
- All Button props - Previous navigation button.

**CarouselNext Props**:
- All Button props - Next navigation button.

**useCarousel Hook**:
- Returns: Object with carouselRef, api, scrollPrev, scrollNext, canScrollPrev, canScrollNext, etc.
- Use within Carousel context for custom controls.

**Example**:
```typescript
import { CarouselRoot, CarouselContent, CarouselItem, CarouselPrevious, CarouselNext } from "@/components/Carousel";

function CarouselExample() {
  return (
    <CarouselRoot opts={{ loop: true }}>
      <CarouselContent>
        <CarouselItem>Slide 1</CarouselItem>
        <CarouselItem>Slide 2</CarouselItem>
        <CarouselItem>Slide 3</CarouselItem>
      </CarouselContent>
      <CarouselPrevious />
      <CarouselNext />
    </CarouselRoot>
  );
}
```
