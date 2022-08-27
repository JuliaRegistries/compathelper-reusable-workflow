# compathelper-workflow

The `compathelper-workflow` is a reusable workflow that makes it easy and convenient to use [CompatHelper.jl](https://github.com/JuliaRegistries/CompatHelper.jl).

## Example Usage

Create a file in your repository at `.github/workflows/CompatHelper.yml` with the following contents:

```yaml
name: CompatHelper
on:
  schedule:
    - cron: 0 0 * * *
  workflow_dispatch:
jobs:
  CompatHelper:
    uses: JuliaRegistries/compathelper-workflow/workflow.yml@v1
    secrets:
      token: ${{ secrets.GITHUB_TOKEN }}
      ssh: ${{ secrets.DOCUMENTER_KEY }}
```

For advanced usage, please see [advanced_usage.md](advanced_usage.md).

## Limitations

- Doesn't work on self-hosted runners. For self-hosted runners, consider using the [CompatHelper composite action](https://github.com/JuliaRegistries/compathelper-action) instead.
