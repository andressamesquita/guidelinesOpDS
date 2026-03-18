### Stepper

**Purpose**: Guide users through a multi-step process with visual indicators, allowing navigation between steps and displaying progress. Semantically, it represents a progress indicator using role="progressbar" or list for steps, enabling keyboard navigation and screen reader support.

**Structure**: Use `Stepper` with an array of `steps`, each containing title, subTitle, and content. Include `Stepper.PreviousButton` and `Stepper.NextButton` for navigation, or `Stepper.Radial` for circular progress. Commonly integrated with forms, wizards, or onboarding flows. Frequently used alongside buttons, inputs, or dialogs for step-by-step interactions.

**Usage Notes**:
- Add padding around the stepper for better layout; it handles step indicators.
- Use for linear workflows; limit steps for clarity.
- Correct: Use for setup wizards or checkouts. Incorrect: Use for non-sequential tasks or single pages.
- Ensure buttons are enabled/disabled based on step; use orientation for layout.
- Customize indicators and alignment for branding.

**Stepper Props**:
- `steps`: Step[] - Array of steps with title, subTitle, content.
- `initialStep`: Number (default: 0) - Starting step index.
- `orientation`: "horizontal" | "vertical" (default: "horizontal") - Layout direction.
- `showIndicator`: Boolean (default: true) - Show step indicators.
- `textAlignment`: "left" | "center" | "right" (default: "left") - Text alignment.
- `className`: String - Additional styles.
- `classNameIndicator`: String - Indicator styles.
- `styleIndicator`: Object - Indicator inline styles.

**Stepper.PreviousButton Props**:
- All button props - Previous step button.

**Stepper.NextButton Props**:
- All button props - Next step button.

**Stepper.Radial Props**:
- `size`: Number (default: 100) - Circle size.
- `weight`: Number (default: 10) - Stroke width.
- `showTitles`: Boolean (default: true) - Show step titles.

**Step Type**:
- `title`: String - Step title.
- `subTitle`: String - Step subtitle.
- `content`: ReactNode - Step content.

**useStepper Hook**:
- Returns: Object with previousStep, nextStep, steps, currentStep.

**Example**:
```typescript
import { Stepper } from "@/components/Stepper";

const steps = [
  { title: "Step 1", subTitle: "Intro", content: <div>Content 1</div> },
  { title: "Step 2", subTitle: "Details", content: <div>Content 2</div> }
];

function StepperExample() {
  return (
    <Stepper steps={steps} initialStep={0}>
      <Stepper.PreviousButton />
      <Stepper.NextButton />
    </Stepper>
  );
}
```