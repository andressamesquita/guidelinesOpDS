### ProgressBar

**Purpose**: Visually communicate the progress of a task, process, or status using a horizontal bar, optionally enriched with contextual label, icon, and percentage.

**Semantic Role**:  
Represents the completion state of a process. It provides feedback to users about ongoing or completed actions, helping them understand status, progression, and urgency.

---

### When to Use

Use `ProgressBar` when:

- Displaying task completion (e.g., uploads, form steps, processing flows)
- Communicating system status (e.g., success, warning, critical states)
- Providing feedback during asynchronous operations
- Showing performance or metrics progression

Commonly used with:

- Cards and dashboards (status overview)
- Forms and multi-step flows (progress indication)
- Lists with status tracking
- Notifications or alerts (paired with severity)

---

### Structure

The component is composed of:

- Optional **icon container** (severity-based styling)
- Optional **progress percentage**
- Optional **label**
- A **LoadingBar** element representing the progress visually
- Severity-based color styling (`primary`, `success`, `warning`, `critical`)

---

### Usage Notes

- Always provide a meaningful `progresValue` between `0` and `100`.
- Use `label` to give context to what is being measured.
- Use `icon` when additional visual context improves comprehension.
- Use `severity` to reflect the semantic meaning of the progress (e.g., success vs critical).
- Avoid overloading the interface with too many progress bars in the same view.
- Keep labels short and descriptive.

---

### Correct Usage

✅ Basic usage:
```tsx
<ProgressBar progresValue={60} label="Uploading files" />
````

✅ With icon and severity:

```tsx
<ProgressBar
  progresValue={80}
  label="Processing data"
  icon="Clock"
  severity="warning"
/>
```

✅ Inside a card or dashboard:

```tsx
<Card>
  <ProgressBar
    progresValue={100}
    label="Completed"
    severity="success"
  />
</Card>
```

---

### Incorrect Usage

❌ Invalid progress value:

```tsx
<ProgressBar progresValue={150} />
```

❌ Missing context (no label or meaning):

```tsx
<ProgressBar progresValue={40} />
```

❌ Overuse in the same context:

```tsx
<>
  <ProgressBar progresValue={20} />
  <ProgressBar progresValue={30} />
  <ProgressBar progresValue={40} />
  <ProgressBar progresValue={50} />
</>
```

❌ Misusing severity (no semantic meaning):

```tsx
<ProgressBar progresValue={10} severity="success" />
```

---

### API

#### `ProgressBar Props`

| Prop           | Type                                                | Default     | Description                                   |
| -------------- | --------------------------------------------------- | ----------- | --------------------------------------------- |
| `progresValue` | `number`                                            | —           | Progress value (0–100)                        |
| `label`        | `string`                                            | —           | Descriptive label for the progress            |
| `icon`         | `IconName \| ReactElement`                          | —           | Optional icon displayed before the bar        |
| `seeProgress`  | `boolean`                                           | `true`      | Controls visibility of the percentage value   |
| `severity`     | `"primary" \| "success" \| "warning" \| "critical"` | `"primary"` | Defines the visual style and semantic meaning |

---

### Variants

* **primary**: Default neutral progress indication
* **success**: Indicates successful or completed states
* **warning**: Indicates attention or intermediate states
* **critical**: Indicates errors or critical conditions

---

### Example

```tsx
import { ProgressBar } from "@/components/ProgressBar";

function ProgressExample() {
  return (
    <div className="flex flex-col gap-4 p-4">
      <ProgressBar
        progresValue={25}
        label="Starting process"
        icon="Play"
      />
      <ProgressBar
        progresValue={65}
        label="In progress"
        severity="warning"
      />
      <ProgressBar
        progresValue={100}
        label="Completed successfully"
        severity="success"
      />
    </div>
  );
}
```

```

