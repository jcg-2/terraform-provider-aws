---
subcategory: "ECR (Elastic Container Registry)"
layout: "aws"
page_title: "AWS: aws_ecr_registry_policy"
description: |-
  Provides an Elastic Container Registry Policy.
---

# Resource: aws_ecr_registry_policy

Provides an Elastic Container Registry Policy.

## Example Usage

```terraform
data "aws_caller_identity" "current" {}

data "aws_region" "current" {}

data "aws_partition" "current" {}

resource "aws_ecr_registry_policy" "example" {
  policy = jsonencode({
    Version = "2012-10-17",
    Statement = [
      {
        Sid    = "testpolicy",
        Effect = "Allow",
        Principal = {
          "AWS" : "arn:${data.aws_partition.current.partition}:iam::${data.aws_caller_identity.current.account_id}:root"
        },
        Action = [
          "ecr:ReplicateImage"
        ],
        Resource = [
          "arn:${data.aws_partition.current.partition}:ecr:${data.aws_region.current.name}:${data.aws_caller_identity.current.account_id}:repository/*"
        ]
      }
    ]
  })
}
```

## Argument Reference

This resource supports the following arguments:

* `policy` - (Required) The policy document. This is a JSON formatted string. For more information about building IAM policy documents with Terraform, see the [AWS IAM Policy Document Guide](https://learn.hashicorp.com/terraform/aws/iam-policy)

## Attribute Reference

This resource exports the following attributes in addition to the arguments above:

* `registry_id` - The registry ID where the registry was created.

## Import

Import ECR Registry Policy using the registry id. For example:

```
$ terraform import aws_ecr_registry_policy.example 123456789012
```
