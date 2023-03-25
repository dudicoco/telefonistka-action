# Telefonistka action

This action runs Telefonistka to help promote changes in a GitOps repo, see [Telefonistka code repo](https://github.com/wayfair-incubator/telefonistka).


## Example usage

```yaml
name: Telefonistka
# Controls when the workflow will run "closed" is used for prmoting changes, "opened"/"synchronize" are needed to warn on drift.
on:
  # Triggers the workflow on push or pull request events but only for the "main" branch
  pull_request:
    types: 
      - closed
      - opened
      - synchronize
    branches: [ "main" ]

jobs:
  telefonistka:
    runs-on: ubuntu-latest
    steps:
      - uses:  Oded-B/telefonistka-action@main
        with:
          repo-token: ${{ secrets.GITHUB_TOKEN }}
                  
```


see https://github.com/Oded-B/telefonistka-actions-example
