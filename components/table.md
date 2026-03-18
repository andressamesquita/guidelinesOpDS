
### Table

**Purpose**: Display structured data in rows and columns, enabling users to scan, compare, and analyze information efficiently across multiple entries.

**Semantic Role**:  
Represents tabular data with clear relationships between headers and corresponding row values. It ensures accessibility and comprehension by maintaining logical data grouping and structure.

---

### When to Use

Use `Table` when:

- ներկայացing structured datasets with multiple rows and columns
- Users need to compare values across categories
- Displaying lists with consistent fields (e.g., users, records, transactions)
- Presenting data-heavy content in dashboards or reports

Commonly used with:

- Cards and containers (data display sections)
- Filters and search inputs (data exploration)
- Pagination components (large datasets)
- Sorting controls (column-based organization)
- Badges, icons, or status indicators inside cells

---

### Structure

The component adapts responsively into two layouts:

**Desktop (Horizontal Table):**
- `<table>` element with `<thead>` and `<tbody>`
- Header row with column titles
- Alternating row background colors
- Horizontal scroll support for overflow

**Mobile (Vertical Table):**
- Each row becomes a stacked card
- Each cell is displayed as a key-value pair:
  - Header (label)
  - Cell content (value)
- Grid layout for better alignment and readability

---

### Usage Notes

- Always provide meaningful `headers` and matching `rows`.
- Ensure each row has the same number of cells as headers.
- Use short, clear labels for headers.
- Avoid overly wide tables; rely on responsive behavior.
- Use formatting (icons, badges, text styles) inside cells for clarity.
- Prefer pagination or filtering for large datasets.
- Ensure content does not overflow excessively (use truncation when needed).

---

### Correct Usage

✅ Basic table:
```tsx
<Table
  data={{
    headers: ["Name", "Email", "Role"],
    rows: [
      ["John Doe", "john@email.com", "Admin"],
      ["Jane Smith", "jane@email.com", "User"],
    ],
  }}
/>
````

✅ With rich content inside cells:

```tsx id="tbl1"
<Table
  data={{
    headers: ["User", "Status"],
    rows: [
      [
        <span>John Doe</span>,
        <Badge variant="success">Active</Badge>,
      ],
      [
        <span>Jane Smith</span>,
        <Badge variant="warning">Pending</Badge>,
      ],
    ],
  }}
/>
```

✅ Inside a card with other controls:

```tsx id="tbl2"
<Card>
  <SearchInput />
  <Table data={data} />
</Card>
```

---

### Incorrect Usage

❌ Mismatched headers and rows:

```tsx id="tbl3"
<Table
  data={{
    headers: ["Name", "Email"],
    rows: [["John", "john@email.com", "Extra"]],
  }}
/>
```

❌ Using for non-tabular content:

```tsx id="tbl4"
<Table
  data={{
    headers: ["Section"],
    rows: [["This is just text content"]],
  }}
/>
```

❌ Overloading with too much data without pagination:

```tsx id="tbl5"
// Avoid rendering hundreds of rows at once
<Table data={largeDataset} />
```

❌ Long unformatted content breaking layout:

```tsx id="tbl6"
<Table
  data={{
    headers: ["Description"],
    rows: [["Very long text without truncation or formatting..."]],
  }}
/>
```

---

### API

#### `Table Props`

| Prop   | Type                                            | Default | Description                   |
| ------ | ----------------------------------------------- | ------- | ----------------------------- |
| `data` | `{ headers: ReactNode[]; rows: ReactNode[][] }` | —       | Structured data for the table |

---

### Data Structure

* **headers**: Array of column titles
* **rows**: Array of rows, each containing an array of cell values
* Each row must match the number of headers

---

### Behavior

* **Responsive**:

  * Desktop: standard table layout
  * Mobile: stacked card layout with key-value pairs

* **Styling**:

  * Alternating row backgrounds (zebra pattern)
  * Primary-colored header
  * Truncated overflow with ellipsis (desktop)

* **Scrolling**:

  * Horizontal scroll enabled on smaller desktop widths

---

### Example

```tsx id="tbl7"
import { Table } from "@/components/Table";

function TableExample() {
  const data = {
    headers: ["Name", "Email", "Status"],
    rows: [
      ["John Doe", "john@email.com", "Active"],
      ["Jane Smith", "jane@email.com", "Pending"],
      ["Alice Brown", "alice@email.com", "Inactive"],
    ],
  };

  return (
    <div className="p-4">
      <Table data={data} />
    </div>
  );
}
```

```
