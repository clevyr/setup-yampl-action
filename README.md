# setup-yampl-action

This action installs [yampl](https://github.com/clevyr/yampl).

See the [yampl](https://github.com/clevyr/yampl#readme) readme for more details on yampl templating capabilities.

# Usage

## Inputs

- `version` - The version of yampl to install.
- `token` - GitHub token.

## Outputs

- `version` - The version of yampl that was installed.

## Example Workflow

Here is an example that fetches a separate deployment repo and patches its configuration.

```yaml
name: Patch Configuration

on: push

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: clevyr/setup-yampl-action@v1
      - run: yampl config.yaml --value sha=${{ github.sha }}
```
