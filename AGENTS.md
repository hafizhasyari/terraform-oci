# AGENTS.md

## Repo purpose

Learning / scratch repo for Terraform on Oracle Cloud Infrastructure (OCI).

## Key facts

- **Single root module** — all `.tf` files at root, no submodules or environments.
- **OCI provider** `oracle/oci` v8.16.0 pinned.
- **Auth:** `SecurityToken` with profile `terraform` (not instance principals or static keys). Ensure valid OCI session tokens before `apply`.
- **Region:** `ap-batam-1`.
- **Resources:** one `oci_core_vcn` (CIDR `172.16.0.0/20`) and one private `oci_core_subnet` (CIDR `172.16.0.0/24`, `prohibit_public_ip_on_vnic = true`) — no compute or IAM resources.
- **Compartment** is the tenancy root (OCID in `terraform.tfvars`). Variable has no default — `terraform.tfvars` is required.
- **State exists** — both resources applied (`terraform.tfstate`, serial 12, outputs populated). `plan` shows no changes; `destroy` deletes live resources.

## Commands

```bash
terraform init
terraform plan
terraform apply
terraform destroy
```

No test/lint/format targets exist.
