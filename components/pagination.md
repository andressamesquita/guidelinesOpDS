### Pagination

**Purpose**: Enable navigation through multiple pages of content, displaying page numbers or dots with previous/next controls. Semantically, it represents pagination navigation using role="navigation" and aria-label="pagination" for accessibility, enabling keyboard navigation and screen reader support.

**Structure**: Render the `Pagination` component with total pages, current page, and change handlers. Commonly integrated with tables, lists, or search results in data-heavy interfaces. Frequently used alongside filters, sorts, or loading indicators for content browsing.

**Usage Notes**:
- Position at the bottom of content; center for balance.
- Use numbers for few pages, dots for many.
- Correct: Use for paginated lists or tables. Incorrect: Use for single-page content or infinite scroll.
- Ensure buttons are disabled appropriately; handle edge cases.
- Customize variant for UI fit.

**Pagination Props**:
- `totalPages`: Number - Total number of pages.
- `currentPage`: Number - Current active page.
- `onPageChange`: Function - Handler for page selection.
- `onPreviousPage`: Function - Optional previous handler.
- `onNextPage`: Function - Optional next handler.
- `variant`: "numbers" | "dots" (default: "numbers") - Display style.

**Example**:
```typescript
import { Pagination } from "@/components/Pagination";

function PaginationExample() {
  const [currentPage, setCurrentPage] = useState(1);

  return (
    <Pagination
      totalPages={10}
      currentPage={currentPage}
      onPageChange={setCurrentPage}
      variant="numbers"
    />
  );
}
```