# terraform-azurerm-log-analytics-workspace
Terraform module to create a log analytics workspace

![Terraform Version](https://img.shields.io/badge/Terraform-0.12.6-green.svg)

## Dependencies

This module has a workaround implemented for Terraform not supporting `depends_on` in modules. To use this, use the `la_depends_on` in the same way you would use `depends_on` when calling the module.
For example usage, please see the examples folder.

## Examples:

```hcl
module "log-analytics" {
  source  = "rink72/log-analytics-workspace/azurerm"
  version = "1.0.0"
  
  name = "rink72-la"
  location = "uswest2"
  resource_group_name = "logging"
  tags = {
      "testTag" = "testValue"
  }
}
```

```hcl
module "log-analytics" {
  source  = "rink72/log-analytics-workspace/azurerm"
  version = "1.0.0"
  
  name = "rink72-la"
  location = "uswest2"
  resource_group_name = "logging"

  solutions = [
      {
      name      = "AzureAutomation",
      publisher = "Microsoft",
      product   = "OMSGallery/AzureAutomation"
    }
  ]

  tags = {
      "testTag" = "testValue"
  }
}
```

## References

Source for module dependency workaround: https://discuss.hashicorp.com/t/tips-howto-implement-module-depends-on-emulation/2305/2
