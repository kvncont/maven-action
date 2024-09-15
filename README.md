# Composite Action Template

This is a composite action for GitHub Actions. Composite actions allow you to combine multiple steps into a single reusable action. This template demonstrates how to create a composite action that takes an input, performs some operations, and produces an output.

## Inputs

- `who-to-greet`: Who to greet. Default is `World`.

## Outputs

- `random-number`: A randomly generated number.

## Example Usage

### Using Required Inputs

```yaml
name: Example Composite Action Usage
on: [push]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repository
        uses: actions/checkout@v4

      - name: Run Composite Action
        uses: kvncont/template-composite-action@main # Replace with your repo name
```

### Using All Inputs

```yaml
name: Example Composite Action Usage with All Inputs
on: [push]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repository
        uses: actions/checkout@v4

      - name: Run Composite Action
        uses: kvncont/template-composite-action@main # Replace with your repo name
        with:
          who-to-greet: "GitHub Actions"
```