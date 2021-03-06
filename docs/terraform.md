## Requirements

No requirements.

## Providers

| Name | Version |
|------|---------|
| helm | n/a |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| chart | (Required) Chart name to be installed | `string` | n/a | yes |
| additional\_tag\_map | Additional tags for appending to tags\_as\_list\_of\_maps. Not added to `tags`. | `map(string)` | `{}` | no |
| atomic | (Optional) If set, installation process purges chart on fail. The wait flag will be set automatically if atomic is used. Defaults to false. | `bool` | `false` | no |
| attributes | Additional attributes (e.g. `1`) | `list(string)` | `[]` | no |
| aws\_account\_id | The AWS account id of the provider being deployed to (e.g. 12345678). Autoloaded from account.tfvars | `string` | `""` | no |
| aws\_assume\_role\_arn | ARN of the IAM role when optionally connecting to AWS via assumed role. Autoloaded from account.tfvars. | `string` | `""` | no |
| aws\_region | The AWS region (e.g. ap-southeast-2). Autoloaded from region.tfvars. | `string` | `""` | no |
| ca\_file | (Optional) Verify certificates of HTTPS-enabled servers using this CA bundle | `string` | `""` | no |
| cert\_file | (Optional) Identify HTTPS client using this SSL certificate file | `string` | `""` | no |
| chart\_version | (Optional) Specify the exact chart version to install. If this is not specified, the latest version is installed | `string` | `""` | no |
| context | Single object for setting entire context at once.<br>See description of individual variables for details.<br>Leave string and numeric variables as `null` to use default value.<br>Individual variable settings (non-null) override settings in context object,<br>except for attributes, tags, and additional\_tag\_map, which are merged. | <pre>object({<br>    enabled             = bool<br>    namespace           = string<br>    environment         = string<br>    stage               = string<br>    name                = string<br>    delimiter           = string<br>    attributes          = list(string)<br>    tags                = map(string)<br>    additional_tag_map  = map(string)<br>    regex_replace_chars = string<br>    label_order         = list(string)<br>    id_length_limit     = number<br>  })</pre> | <pre>{<br>  "additional_tag_map": {},<br>  "attributes": [],<br>  "delimiter": null,<br>  "enabled": true,<br>  "environment": null,<br>  "id_length_limit": null,<br>  "label_order": [],<br>  "name": null,<br>  "namespace": null,<br>  "regex_replace_chars": null,<br>  "stage": null,<br>  "tags": {}<br>}</pre> | no |
| create\_namespace | (Optional) Create the namespace if it does not yet exist. Defaults to false. | `bool` | `false` | no |
| delimiter | Delimiter to be used between `namespace`, `environment`, `stage`, `name` and `attributes`.<br>Defaults to `-` (hyphen). Set to `""` to use no delimiter at all. | `string` | `null` | no |
| dependency\_update | (Optional) Runs helm dependency update before installing the chart. Defaults to false. | `bool` | `false` | no |
| devel | (Optional) Use chart development versions, too. Equivalent to version '>0.0.0-0'. If version is set, this is ignored | `bool` | `false` | no |
| disable\_openapi\_validation | (Optional) If set, the installation process will not validate rendered templates against the Kubernetes OpenAPI Schema. Defaults to false. | `bool` | `false` | no |
| disable\_webhooks | (Optional) Prevent hooks from running | `bool` | `false` | no |
| enabled | Set to false to prevent the module from creating any resources | `bool` | `null` | no |
| environment | Environment, e.g. 'uw2', 'us-west-2', OR 'prod', 'staging', 'dev', 'UAT' | `string` | `null` | no |
| force\_update | (Optional) Force resource update through delete/recreate if needed | `bool` | `true` | no |
| id\_length\_limit | Limit `id` to this many characters.<br>Set to `0` for unlimited length.<br>Set to `null` for default, which is `0`.<br>Does not affect `id_full`. | `number` | `null` | no |
| k8s\_namespace | (Optional) The namespace to install the release into. Defaults to default. | `string` | `"default"` | no |
| key\_file | (Optional) Identify HTTPS client using this SSL key file | `string` | `""` | no |
| keyring | (Optional) Location of public keys used for verification. Used only if verify is true. Defaults to /.gnupg/pubring.gpg in the location set by home | `string` | `"/.gnupg/pubring.gpg"` | no |
| kubeconfig\_context | (Required) The context to use from the `kubeconfig` file | `string` | `""` | no |
| kubeconfig\_path | The path to `kubeconfig` file | `string` | `"~/.kube/config"` | no |
| label\_order | The naming order of the id output and Name tag.<br>Defaults to ["namespace", "environment", "stage", "name", "attributes"].<br>You can omit any of the 5 elements, but at least one must be present. | `list(string)` | `null` | no |
| lint | (Optional) Run the helm chart linter during the plan. Defaults to false. | `bool` | `false` | no |
| name | Solution name, e.g. 'app' or 'jenkins' | `string` | `null` | no |
| namespace | Namespace, which could be your organization name or abbreviation, e.g. 'eg' or 'cp' | `string` | `null` | no |
| postrender | (Optional) Configure a command to run after helm renders the manifest which can alter the manifest contents. | `string` | `""` | no |
| recreate\_pods | (Optional) On update performs pods restart for the resource if applicable | `bool` | `false` | no |
| regex\_replace\_chars | Regex to replace chars with empty string in `namespace`, `environment`, `stage` and `name`.<br>If not set, `"/[^a-zA-Z0-9-]/"` is used to remove all characters other than hyphens, letters and digits. | `string` | `null` | no |
| release\_name | (Required) Release name | `string` | `""` | no |
| render\_subchart\_notes | (Optional) If set, render subchart notes along with the parent. Defaults to true. | `bool` | `true` | no |
| replace | (Optional) Re-use the given name, even if that name is already used. This is unsafe in production. Defaults to false. | `bool` | `false` | no |
| repository | (Optional) Repository URL where to locate the requested chart. | `string` | `""` | no |
| repository\_password | (Optional) Password for HTTP basic authentication | `string` | `""` | no |
| repository\_username | (Optional) Username for HTTP basic authentication | `string` | `""` | no |
| reuse\_values | (Optional) Reuse values from previous revision when upgrading a release. Same as --reuse-values flag in Helm CLI. Default is false | `bool` | `false` | no |
| set | (Optional) Value block with custom values to be merged with the values yaml | <pre>list(object({<br>    name  = string<br>    value = string<br>  }))</pre> | <pre>[<br>  {<br>    "name": "",<br>    "value": ""<br>  }<br>]</pre> | no |
| set\_sensitive | (Optional) Value block with custom sensitive values to be merged with the values yaml that won't be exposed in the plan's diff | <pre>list(object({<br>    name  = string<br>    value = string<br>  }))</pre> | <pre>[<br>  {<br>    "name": "",<br>    "value": ""<br>  }<br>]</pre> | no |
| skip\_crds | (Optional) If set, no CRDs will be installed. By default, CRDs are installed if not already present. Defaults to false. | `bool` | `false` | no |
| stage | Stage, e.g. 'prod', 'staging', 'dev', OR 'source', 'build', 'test', 'deploy', 'release' | `string` | `null` | no |
| tags | Additional tags (e.g. `map('BusinessUnit','XYZ')` | `map(string)` | `{}` | no |
| timeout | (Optional) Time in seconds to wait for any individual kubernetes operation | `number` | `30` | no |
| values | (Optional) List of values in raw yaml to pass to helm. Values will be merged, in order, as Helm does with multiple -f options | `list(any)` | `[]` | no |
| verify | (Optional) Verify the package before installing it. Helm uses a provenance file to verify the integrity of the chart; this must be hosted alongside the chart. For more information see the Helm Documentation. Defaults to false. | `bool` | `false` | no |
| wait | (Optional) Will wait until all Pods, PVCs, Services, and minimum number of Pods of a Deployment are in a ready state before marking the release as successful. It will wait for as long as timeout. Default is true | `bool` | `false` | no |

## Outputs

No output.

