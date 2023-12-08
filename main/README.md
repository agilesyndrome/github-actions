## CI Job

There is a root CI job that attempts to build/run based on very opinionated defaults.
This might not work for you

```yaml
jobs:
  ci:
    runs-on: ubuntu-latest
    steps:
      - name: CI
        uses: agilesyndrome/github-actions@main
        with:
          makefile_target: ci

```

### Inputs

| Input | Default | Purpose |
|:------|:--------|:----------------|
| unshallow | 1       | Runs `git fetch --prune --unshallow` after checkout
| action_version | main | Branch/Tag/Sha of agilesyndrome/github-actions
| asdf_tool_versions_file | .tool-versions | Where is the ASDF tool versions file located?
| makefile_target | `empty` | If set, will run `make ${{makefile_target}}`

### Steps (in order)

(*) Conditional Step: See input list

1. Checkout Code
2. Unshallow (*)
3. Setup ASDF Environment
4. Makefile Target
5. GoRelease
