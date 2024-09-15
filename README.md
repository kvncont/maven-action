# Maven Build Action

This is a composite action for GitHub Actions designed to streamline the Maven build process. Composite actions allow you to combine multiple steps into a single reusable action. This action sets up the JDK, configures Maven, and runs specified Maven goals, making it easier to manage Java projects in your CI/CD pipeline.

## Inputs

- `jdk-distribution`: JDK distribution to use. Default is `corretto`.
- `jdk-version`: JDK version to use. Default is `21`.
- `pom-file`: Path to the Pom file. Default is `./pom.xml`.
- `mvn-goals`: Maven goals to execute. Default is `clean package`.
- `mvn-opts`: Maven options to configure. Default is `-Xmx2048m`.

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
        uses: kvncont/maven-action@main # Remember use a tag instead of main
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
        uses: kvncont/maven-action@main # Remember use a tag instead of main
        with:
          jdk-distribution: corretto
          jdk-version: 21
          pom-file: test-action/pom.xml
          mvn-goals: clean package
          mvn-opts: -Xmx2048m
```