# UpCloud compute

TODO: implement

Example usage:

```
provider "upcloud" {
  username        = "<Your username>"
  password        = "<Your password>"
}

module "compute" {
  source          = "TaitoUnited/compute/upcloud"
  version         = "1.0.0"

  virtual_machines = yamldecode(file("${path.root}/../infra.yaml"))["virtualMachines"]
}
```

Example YAML:

```
virtualMachines:
  - hostname: terraform.example.tld
    zone: de-fra1
    plan: 1xCPU-1GB
    ...
```

YAML attributes:

- See variables.tf for all the supported YAML attributes.
- See [upcloud_server](https://registry.terraform.io/providers/UpCloudLtd/upcloud/latest/docs/resources/upcloud_server) for attribute descriptions.

Combine with the following modules to get a complete infrastructure defined by YAML:

- [Compute](https://registry.terraform.io/modules/TaitoUnited/compute/upcloud)

Similar modules are also available for Azure, Google Cloud, and DigitalOcean. All modules are used by [infrastructure templates](https://taitounited.github.io/taito-cli/templates#infrastructure-templates) of [Taito CLI](https://taitounited.github.io/taito-cli/). TIP: See also [AWS project resources](https://registry.terraform.io/modules/TaitoUnited/project-resources/aws), [Full Stack Helm Chart](https://github.com/TaitoUnited/taito-charts/blob/master/full-stack), and [full-stack-template](https://github.com/TaitoUnited/full-stack-template).

Contributions are welcome!
