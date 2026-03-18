### LoadingBar

**Purpose**: Display a progress bar for loading states or determinate progress, providing visual feedback on operations. Semantically, it represents a progress bar using role="progressbar" for accessibility, enabling screen reader support.

**Structure**: Render the `LoadingBar` component with a value for progress. Commonly integrated with buttons, forms, or pages during loading. Frequently used alongside spinners or text for status updates.

**Usage Notes**:
- Position at the top or bottom; it handles animation.
- Use for file uploads or steps; set value for progress.
- Correct: Use for determinate progress. Incorrect: Use for indeterminate loading or as a spinner.
- Ensure value updates; customize colors for branding.
- Integrate with async operations.

**LoadingBar Props**:
- `value`: Number (0-100) - Progress value.
- `className`: String - Indicator styles.
- `containerClassName`: String - Container styles.
- All Radix Progress.Root props.

**Example**:
```typescript
import { LoadingBar } from "@/components/LoadingBar";

function LoadingBarExample() {
  const [progress, setProgress] = useState(0);

  return (
    <LoadingBar value={progress} />
  );
}
```