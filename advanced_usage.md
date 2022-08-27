# Advanced Usage

## Subdirectory packages

```yaml
jobs:
  CompatHelper:
    uses: JuliaRegistries/compathelper-workflow/workflow.yml@v1
    with:
      cmd: |
        subdirs = ["foo", "bar"]
        CompatHelper.main(; subdirs)
      compathelper_version: '3'
      julia_version: '1'
    secrets:
      token: ${{ secrets.GITHUB_TOKEN }}
      ssh: ${{ secrets.DOCUMENTER_KEY }}
```
