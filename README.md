# Terraform OCI — Learning Repo

A learning / scratch repo for Terraform on Oracle Cloud Infrastructure (OCI).

## Resources

- **VCN** — `oci_core_vcn.internal` (CIDR `172.16.0.0/20`)
- **Subnet** — `oci_core_subnet.dev` (CIDR `172.16.0.0/24`, private, no public IP)

## Prerequisites

- [Terraform](https://developer.hashicorp.com/terraform/downloads) >= 1.x
- OCI account with a valid [Security Token](https://docs.oracle.com/en-us/iaas/Content/Identity/Concepts/signing_into_console.htm) — configure profile `terraform` in your OCI config file
- `terraform.tfvars` with your tenancy OCID:

```hcl
compartment_id = "ocid1.tenancy.oc1..aaaaaa..."
region         = "ap-batam-1"
```

## Commands

```bash
terraform init
terraform plan
terraform apply
terraform destroy
```

## State

Both resources have been applied. Running `plan` shows no changes; `destroy` deletes live resources.
