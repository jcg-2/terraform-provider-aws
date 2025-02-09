---
subcategory: "API Gateway V2"
layout: "aws"
page_title: "AWS: aws_apigatewayv2_route_response"
description: |-
  Manages an Amazon API Gateway Version 2 route response.
---

# Resource: aws_apigatewayv2_route_response

Manages an Amazon API Gateway Version 2 route response.
More information can be found in the [Amazon API Gateway Developer Guide](https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-websocket-api.html).

## Example Usage

### Basic

```terraform
resource "aws_apigatewayv2_route_response" "example" {
  api_id             = aws_apigatewayv2_api.example.id
  route_id           = aws_apigatewayv2_route.example.id
  route_response_key = "$default"
}
```

## Argument Reference

This resource supports the following arguments:

* `api_id` - (Required) API identifier.
* `route_id` - (Required) Identifier of the [`aws_apigatewayv2_route`](/docs/providers/aws/r/apigatewayv2_route.html).
* `route_response_key` - (Required) Route response key.
* `model_selection_expression` - (Optional) The [model selection expression](https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-websocket-api-selection-expressions.html#apigateway-websocket-api-model-selection-expressions) for the route response.
* `response_models` - (Optional) Response models for the route response.

## Attribute Reference

This resource exports the following attributes in addition to the arguments above:

* `id` - Route response identifier.

## Import

Import `aws_apigatewayv2_route_response` using the API identifier, route identifier and route response identifier. For example:

```
$ terraform import aws_apigatewayv2_route_response.example aabbccddee/1122334/998877
```
