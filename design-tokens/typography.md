## Typography Tokens

Opala DS uses typography tokens organized around t-shirt sizes (large, medium, small) to create multiple levels of hierarchy. The system includes body text and headings with optional "strong" variants for emphasis, all based on the Montserrat font family for consistency and readability.

Always use Medium Body size for body text. Only use small very sparingly, as it is hard to read. Make sure to use varying sizes corresponding to the level of hierarchy. For example, heading text should be styled larger than body text.

### Design Philosophy

- T-shirt sizing (large, medium, small) provides intuitive hierarchy
- Strong variants available for body text to create emphasis without changing size
- All headings use strong weight by default
- Font sizes and line heights are optimized for UI density and readability
- Typography tokens include font family, size, weight, line height, and letter spacing as a complete style package
- Montserrat is the primary font for all UI text, ensuring a clean and modern look

### Font Families

**font.family.default**
- Value: Montserrat (with system fallbacks)
- Usage: All standard UI text including headings and body text

**font.family.display**
- Value: Montserrat (with system fallbacks)
- Usage: Display text for expressive moments and important announcements

**font.family.mono**
- Value: System monospace (with fallbacks)
- Usage: Code and monospace content

### Font Weights

**font.weight.default**
- Value: 400
- Usage: Standard body text weight

**font.weight.strong**
- Value: 600
- Usage: Emphasized text and all headings

### Display Text

Always use Medium Body size for body text. Only use small very sparingly, as it is hard to read.

#### Display

Large display size for expressive moments and important announcements.

```css
.example {
  font-family: var(--text-display-font-family);
  font-size: var(--text-display-font-size);
  font-weight: var(--text-display-font-weight);
  letter-spacing: var(--text-display-letter-spacing);
  line-height: var(--text-display-line-height);
}
```

### Heading Tokens

#### Headings

##### Large

- Usage: Primary page title within large views, largest heading size

```css
.example {
  font-family: var(--text-heading-large-font-family);
  font-size: var(--text-heading-large-font-size);
  font-weight: var(--text-heading-large-font-weight);
  letter-spacing: var(--text-heading-large-letter-spacing);
  line-height: var(--text-heading-large-line-height);
}
```

##### Medium

- Usage: Section headers

```css
.example {
  font-family: var(--text-heading-medium-font-family);
  font-size: var(--text-heading-medium-font-size);
  font-weight: var(--text-heading-medium-font-weight);
  letter-spacing: var(--text-heading-medium-letter-spacing);
  line-height: var(--text-heading-medium-line-height);
}
```

##### Small

- Usage: Subsection headers

```css
.example {
  font-family: var(--text-heading-small-font-family);
  font-size: var(--text-heading-small-font-size);
  font-weight: var(--text-heading-small-font-weight);
  letter-spacing: var(--text-heading-small-letter-spacing);
  line-height: var(--text-heading-small-line-height);
}
```

### Body Text Tokens

#### Body

##### Large

- Usage: Large display size usually saved for expressive moments, important announcements, and multiline text. Has a "strong" variant for additional emphasis.

```css
.example {
  font-family: var(--text-body-large-font-family);
  font-size: var(--text-body-large-font-size);
  font-weight: var(--text-body-large-font-weight);
  letter-spacing: var(--text-body-large-letter-spacing);
  line-height: var(--text-body-large-line-height);
}

.example-strong {
  font-family: var(--text-body-large-strong-font-family);
  font-size: var(--text-body-large-strong-font-size);
  font-weight: var(--text-body-large-strong-font-weight);
  letter-spacing: var(--text-body-large-strong-letter-spacing);
  line-height: var(--text-body-large-strong-line-height);
}
```

##### Medium

- Usage: Default for most UI elements (inputs, buttons, labels)

```css
.example {
  font-family: var(--text-body-medium-font-family);
  font-size: var(--text-body-medium-font-size);
  font-weight: var(--text-body-medium-font-weight);
  letter-spacing: var(--text-body-medium-letter-spacing);
  line-height: var(--text-body-medium-line-height);
}

.example-strong {
  font-family: var(--text-body-medium-strong-font-family);
  font-size: var(--text-body-medium-strong-font-size);
  font-weight: var(--text-body-medium-strong-font-weight);
  letter-spacing: var(--text-body-medium-strong-letter-spacing);
  line-height: var(--text-body-medium-strong-line-height);
}
```

##### Small

- Usage: Compact UI like badges, avatars, and metadata

```css
.example {
  font-family: var(--text-body-small-font-family);
  font-size: var(--text-body-small-font-size);
  font-weight: var(--text-body-small-font-weight);
  letter-spacing: var(--text-body-small-letter-spacing);
  line-height: var(--text-body-small-line-height);
}

.example-strong {
  font-family: var(--text-body-small-strong-font-family);
  font-size: var(--text-body-small-strong-font-size);
  font-weight: var(--text-body-small-strong-font-weight);
  letter-spacing: var(--text-body-small-strong-letter-spacing);
  line-height: var(--text-body-small-strong-line-height);
}
```

### Token Structure

Typography tokens are composite values that include:
- Font family reference
- Font size
- Font weight
- Line height
- Letter spacing

Use the complete token rather than individual properties to ensure consistency.

### Implementation

Tokens are defined in the design system and compiled to CSS. Apply full typography tokens using CSS variables or utility classes. Example: `font-size: var(--text-body-small-font-size)`.

### Selection Guidelines

**For headings:**
- Use heading.large for page titles in large views
- Use heading.medium for section headers
- Use heading.small for subsection headers

**For body text:**
- Use body.medium as the default for most UI elements (inputs, buttons, labels)
- Use body.large for multiline content and emphasized text blocks
- Use body.small for compact UI like badges, avatars, and metadata
- Add -strong variants for emphasis without changing size