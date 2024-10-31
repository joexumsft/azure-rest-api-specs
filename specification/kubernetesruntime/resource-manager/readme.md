# kubernetesruntime

> see https://aka.ms/autorest

This is the AutoRest configuration file for kubernetesruntime.

## Getting Started

To build the SDKs for My API, simply install AutoRest via `npm` (`npm install -g autorest`) and then run:

> `autorest readme.md`

To see additional help and options, run:

> `autorest --help`

For other options on installation see [Installing AutoRest](https://aka.ms/autorest/install) on the AutoRest github page.

---

## Configuration

### Basic Information

These are the global settings for the kubernetesruntime.

``` yaml
openapi-type: arm
openapi-subtype: rpaas
tag: package-2024-03-01

suppressions:
  - code: ConsistentPatchProperties
    from: kubernetesruntime.json
    reason: The tooling doens't check properties in derived models of discriminated unions.
  - code: GuidUsage
    from: kubernetesruntime.json
    where: $.definitions["Azure.Core.uuid"].format
    reason: The definition is used for AAD object ids, which are UUIDs.

```
### Tag: package-preview-2023-10-01

These settings apply only when `--tag=package-preview-2023-10-01` is specified on the command line.

```yaml $(tag) == 'package-preview-2023-10-01'
input-file:
  - Microsoft.KubernetesRuntime/preview/2023-10-01-preview/kubernetesruntime.json
```

### Tag: package-2024-03-01

These settings apply only when `--tag=package-2024-03-01` is specified on the command line.

```yaml $(tag) == 'package-2024-03-01'
input-file:
  - Microsoft.KubernetesRuntime/stable/2024-03-01/kubernetesruntime.json
```

---

# Code Generation

## Swagger to SDK

This section describes what SDK should be generated by the automatic system.
This is not used by Autorest itself.

``` yaml $(swagger-to-sdk)
swagger-to-sdk:
  - repo: azure-sdk-for-python
  - repo: azure-sdk-for-java
  - repo: azure-sdk-for-go
  - repo: azure-sdk-for-js
  - repo: azure-sdk-for-net
  - repo: azure-sdk-for-ruby
    after_scripts:
      - bundle install && rake arm:regen_all_profiles['azure_mgmt_kubernetesruntime']
  - repo: azure-resource-manager-schemas
```

## Go

See configuration in [readme.go.md](./readme.go.md)

## Python

See configuration in [readme.python.md](./readme.python.md)

## Ruby

See configuration in [readme.ruby.md](./readme.ruby.md)

## TypeScript

See configuration in [readme.typescript.md](./readme.typescript.md)

## CSharp

See configuration in [readme.csharp.md](./readme.csharp.md)