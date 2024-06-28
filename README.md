# Precaution Analysis Action

Analyze your source code using Precaution via [precli](https://github.com/securesauce/precli).

## Usage

Here is a minimal complete example to create a Code Scanning action using Precaution.

```yaml
name: Precaution

on:
  workflow_dispatch:

jobs:
  analyze:
    runs-on: ubuntu-latest
    permissions:
      # required for all workflows
      security-events: write
      # only required for workflows in private repositories
      actions: read
      contents: read
    steps:
      - name: Perform Precaution Analysis
        uses: securesauce/precli-action@v1
```

## Inputs

| Name | Description | Required | Default Value |
|--|--|--|--|
| path | The source file(s) or directory(s) to be analyzed | False | `"."` |
| disable | A comma-separated list of rule IDs or names to disable | False | `"DEFAULT"` |
