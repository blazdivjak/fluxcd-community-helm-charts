# flux2-multi-tenancy

![Version: 0.0.2](https://img.shields.io/badge/Version-0.0.2-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square)

A Helm chart for flux2-multi-tenancy

## Source Code

* <https://github.com/fluxcd/flux2-multi-tenancy>

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://kyverno.github.io/kyverno | kyverno | 2.1.4 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| kyverno.enabled | bool | `false` | Enable kyverno to be installed as dependencies. |
| policy.rules.helmReleaseSourceRefNamespace.exclude.namespaces | list | `["flux-system"]` | List of namestace to ignore. |
| policy.rules.kustomizationSourceRefNamespace.exclude.namespaces | list | `["flux-system"]` | List of namestace to ignore. |
| policy.rules.serviceAccountName.exclude.namespaces | list | `["flux-system"]` | List of namestace to ignore. |
| policy.rules.serviceAccountName.match.kinds | list | `["Kustomization","HelmRelease"]` | The `Kinds` we want to check that a serviceAccountName is set |
| policy.validationFailureAction | string | `"enforce"` | Tells Kyverno if the resource being validated should be allowed but reported (`audit`) or blocked (`enforce`). |
