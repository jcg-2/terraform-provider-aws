---
subcategory: "Lightsail"
layout: "aws"
page_title: "AWS: aws_lightsail_bucket_resource_access"
description: |-
  Provides a lightsail resource access to a bucket.
---

# Resource: aws_lightsail_bucket_resource_access

Provides a lightsail resource access to a bucket.

## Example Usage

```terraform
resource "aws_lightsail_bucket" "test" {
  name      = "mytestbucket"
  bundle_id = "small_1_0"
}

resource "aws_lightsail_instance" "test" {
  name              = "mytestinstance"
  availability_zone = "us-east-1b"
  blueprint_id      = "amazon_linux_2"
  bundle_id         = "nano_1_0"
}

resource "aws_lightsail_bucket_resource_access" "test" {
  bucket_name   = aws_lightsail_bucket_resource_access.test.id
  resource_name = aws_lightsail_instance.id
}
```

## Argument Reference

This resource supports the following arguments:

* `bucket_name` - (Required) The name of the bucket to grant access to.
* `resource_name` - (Required) The name of the resource to be granted bucket access.

## Attribute Reference

This resource exports the following attributes in addition to the arguments above:

* `id` - A combination of attributes separated by a `,` to create a unique id: `bucket_name`,`resource_name`

## Import

Import `aws_lightsail_bucket_resource_access` using the `id` attribute. For example:

```
$ terraform import aws_lightsail_bucket_resource_access.test example-bucket,example-instance
```
