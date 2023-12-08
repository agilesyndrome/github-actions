# ASDF

## Example
```yaml
- name: Setup ASDF environment
  id: asdf
  uses: agilesyndrome/github-actions/asdf@main
```

## Example Filter
```yaml
if: "${{ steps.asdf.outputs.GORELEASER_VERSION != '' }}"
```


## Inputs


| Input                     | Default          | Purpose                                            |
|:--------------------------|:-----------------|:---------------------------------------------------|
| asdf_tool_versions_file   | `.tool-versions` | Location of the ASDF format .tool-versions file |
| {asdf_plugin_name}_action | *varies* | Use to override the version of a Github action for a specific plugin. |

## Outputs


* {ASDF_PLUGIN_NAME}_VERSION : The version detected from the asdf .tool-versions file. 
