---
subcategory: "Pinpoint"
layout: "aws"
page_title: "AWS: aws_pinpoint_gcm_channel"
description: |-
  Provides a Pinpoint GCM Channel resource.
---

# Resource: aws_pinpoint_gcm_channel

Provides a Pinpoint GCM Channel resource.

~> **Note:** Api Key argument will be stored in the raw state as plain-text.
[Read more about sensitive data in state](https://www.terraform.io/docs/state/sensitive-data.html).

## Example Usage

```terraform
resource "aws_pinpoint_gcm_channel" "gcm" {
  application_id = aws_pinpoint_app.app.application_id
  api_key        = "api_key"
}

resource "aws_pinpoint_app" "app" {}
```

## Argument Reference

This resource supports the following arguments:

* `application_id` - (Required) The application ID.
* `api_key` - (Required) Platform credential API key from Google.
* `enabled` - (Optional) Whether the channel is enabled or disabled. Defaults to `true`.

## Attribute Reference

This resource exports no additional attributes.

## Import

Import Pinpoint GCM Channel using the `application-id`. For example:

```
$ terraform import aws_pinpoint_gcm_channel.gcm application-id
```
