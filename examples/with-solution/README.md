# Simple Log Analytics example

Configuration in this directory creates a test resource group and then deploys a single log analytics workspace in it.
It also deploys the Azure Automation solution in to the workspace.
This also demonstrates the usage of the `la_depends_on` variable.

## Usage

To run this example you need to execute:

```bash
$ terraform init
$ terraform plan
$ terraform apply
```

Note that this example may create resources which cost money. Run `terraform destroy` when you don't need these resources.