# terraform-docs-example



# Generating terraform-docs  markdown and output to README.md  

    terraform-docs markdown ./ --output-file README.md --output-mode inject

# Output 



This will add the markdown, without overwriting README.MD file 
There are two modes "--output-mode inject" and "--output-mode replace" 

# [Optional] Terraform code provisioning Private , Public ACL disabled S3 bucket


Enter the directory with code , run : 

    terraform init

    terraform plan

    terraform apply

### Example output 


    Apply complete! Resources: 0 added, 0 changed, 0 destroyed.

    Outputs:

    s3_bucket_name = "dev-cloudtipss-e495296a"
    (base) vrider@vladyslvslaptop terraform-docs-example % terraform apply
    random_id.bucket_suffix: Refreshing state... [id=5JUpag]
    aws_s3_bucket.example: Refreshing state... [id=dev-cloudtipss-e495296a]
    aws_s3_bucket_public_access_block.example_block: Refreshing state... [id=dev-cloudtipss-e495296a]
    aws_s3_bucket_ownership_controls.example: Refreshing state... [id=dev-cloudtipss-e495296a]
    aws_s3_bucket_acl.example_acl: Refreshing state... [id=dev-cloudtipss-e495296a,private]

    No changes. Your infrastructure matches the configuration.

    Terraform has compared your real infrastructure against your configuration and found no differences, so no changes are needed.

    Apply complete! Resources: 0 added, 0 changed, 0 destroyed.

    Outputs:

    s3_bucket_name = "dev-cloudtipss-e495296a"

# Destroying S3 bucket and relevant resources

    terraform destroy

    
<!-- BEGIN_TF_DOCS -->
## Requirements

No requirements.

## Providers

| Name | Version |
|------|---------|
| <a name="provider_aws"></a> [aws](#provider\_aws) | 5.20.1 |
| <a name="provider_random"></a> [random](#provider\_random) | 3.5.1 |

## Modules

No modules.

## Resources

| Name | Type |
|------|------|
| [aws_s3_bucket.example](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/s3_bucket) | resource |
| [aws_s3_bucket_acl.example_acl](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/s3_bucket_acl) | resource |
| [aws_s3_bucket_ownership_controls.example](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/s3_bucket_ownership_controls) | resource |
| [aws_s3_bucket_public_access_block.example_block](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/s3_bucket_public_access_block) | resource |
| [random_id.bucket_suffix](https://registry.terraform.io/providers/hashicorp/random/latest/docs/resources/id) | resource |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_env"></a> [env](#input\_env) | Environment name | `string` | `"dev"` | no |
| <a name="input_project"></a> [project](#input\_project) | Project name | `string` | `"cloudtipss"` | no |

## Outputs

| Name | Description |
|------|-------------|
| <a name="output_s3_bucket_name"></a> [s3\_bucket\_name](#output\_s3\_bucket\_name) | n/a |
<!-- END_TF_DOCS -->

# Test Terraform Docs PR