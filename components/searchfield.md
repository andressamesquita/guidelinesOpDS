### SearchField

**Purpose**: Provide a text input for search queries with optional voice input via mic button, supporting validation, helper text, and character limits. Semantically, it represents a search input using type="search" and role="searchbox" for accessibility, enabling keyboard navigation and screen reader support.

**Structure**: Render the `SearchField` component with label, optional helper text, and mic button. Commonly integrated with lists, dropdowns, or filters in search interfaces. Frequently used alongside buttons, icons, or results displays for query handling.

**Usage Notes**:
- Add padding around the field for better layout; it includes icons and input.
- Use for search functionality; mic for voice input.
- Correct: Use for search bars or filters. Incorrect: Use for general form inputs without search intent.
- Ensure onChange handles queries; use variant for error states.
- Show helper text for guidance; limit maxLength for constraints.

**SearchField Props**:
- `label`: String - Field label.
- `size`: "sm" | "md" | "lg" (default: "md") - Field size.
- `values`: Any - Initial values (if applicable).
- `helperText`: String - Helper message.
- `onMicClick`: Function - Mic button handler.
- `onChange`: Function - Input change handler.
- `onSearchResults`: Function - Search results handler.
- `maxLength`: Number - Max characters.
- `disabled`: Boolean (default: false) - Disables the field.
- `variant`: "default" | "error" etc. (default: "default") - Border variant.
- All standard input props.

**Example**:
```typescript
import { SearchField } from "@/components/SearchField";

function SearchFieldExample() {
  const [query, setQuery] = useState("");

  return (
    <SearchField
      label="Search"
      value={query}
      onChange={(e) => setQuery(e.target.value)}
      onMicClick={() => alert("Voice search")}
      helperText="Type to search"
      maxLength={50}
    />
  );
}
```