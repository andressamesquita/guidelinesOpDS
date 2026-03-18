````markdown
### LoginGovButton

**Purpose**: Provide a standardized call-to-action for authentication via Gov.br, ensuring visual consistency and trust when users log in using a government account.

**Semantic Role**:  
Represents a primary authentication action. It should be used as an entry point for identity verification through Gov.br, typically in login, onboarding, or secure service access flows.

---

### When to Use

Use `LoginGovButton` when:

- Users need to authenticate using their Gov.br account.
- You want to highlight an official and secure login method.
- The flow involves identity validation for government services.

Commonly used with:

- Form containers (e.g., login or registration forms)
- Authentication layouts (e.g., centered card, modal, or full-page login)
- Other authentication options (e.g., email/password, social login buttons)

---

### Structure

The component is a styled `<button>` element that includes:

- A left-aligned label (`Entre com sua conta`)
- A directional icon (`ArrowRight`)
- A right-aligned Gov.br logo
- Variant-based styling (`primary` or `secondary`)

---

### Usage Notes

- The button is full-width by default (`w-full`) with a minimum width of 300px.
- Always use it as a **standalone prominent action** in the interface.
- Do not override the internal structure (text, icon, logo) unless strictly necessary.
- Ensure sufficient spacing around the button to maintain visual hierarchy.
- Use the `primary` variant for main login actions and `secondary` for alternative emphasis.

---

### Correct Usage

✅ Use as the main login action:
```tsx
<LoginGovButton onClick={handleLogin} />
````

✅ Use inside a login container:

```tsx
<div className="max-w-md mx-auto p-6">
  <LoginGovButton />
</div>
```

✅ Use alongside other login methods (with clear separation):

```tsx
<>
  <LoginGovButton />
  <Divider />
  <EmailLoginForm />
</>
```

---

### Incorrect Usage

❌ Do not use as a generic button:

```tsx
<LoginGovButton>Submit</LoginGovButton>
```

❌ Do not remove or replace the Gov.br branding:

```tsx
// Avoid modifying internal logo or label
```

❌ Do not use multiple times in the same context:

```tsx
<>
  <LoginGovButton />
  <LoginGovButton />
</>
```

❌ Do not use for non-authentication actions:

```tsx
<LoginGovButton onClick={handleDownload} />
```

---

### API

#### `LoginGovButton Props`

Extends: `React.ButtonHTMLAttributes<HTMLButtonElement>`

| Prop        | Type                       | Default     | Description                                               |
| ----------- | -------------------------- | ----------- | --------------------------------------------------------- |
| `variant`   | `"primary" \| "secondary"` | `"primary"` | Defines the visual style of the button                    |
| `className` | `string`                   | —           | Additional CSS classes for customization                  |
| `...props`  | `button attributes`        | —           | Native button props (e.g., `onClick`, `disabled`, `type`) |

---

### Variants

* **primary**:
  Uses `bg-opala-primary-default` with hover state.
  Recommended for main login actions.

* **secondary**:
  Uses `bg-opala-success-enabled` with hover state.
  Suitable for alternative or contextual login emphasis.

---

### Example

```tsx
import { LoginGovButton } from "@/components/LoginGovButton";

function LoginExample() {
  const handleLogin = () => {
    console.log("Redirecting to Gov.br...");
  };

  return (
    <div className="flex flex-col items-center justify-center min-h-screen p-4">
      <LoginGovButton onClick={handleLogin} />
    </div>
  );
}
```

```
```
