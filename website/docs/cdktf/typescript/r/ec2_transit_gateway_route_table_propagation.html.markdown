---
subcategory: "Transit Gateway"
layout: "aws"
page_title: "AWS: aws_ec2_transit_gateway_route_table_propagation"
description: |-
  Manages an EC2 Transit Gateway Route Table propagation
---


<!-- Please do not edit this file, it is generated. -->
# Resource: aws_ec2_transit_gateway_route_table_propagation

Manages an EC2 Transit Gateway Route Table propagation.

## Example Usage

```typescript
// Code generated by 'cdktf convert' - Please report bugs at https://cdk.tf/bug
import { Construct } from "constructs";
import { Token, TerraformStack } from "cdktf";
/*
 * Provider bindings are generated by running `cdktf get`.
 * See https://cdk.tf/provider-generation for more details.
 */
import { Ec2TransitGatewayRouteTablePropagation } from "./.gen/providers/aws/ec2-transit-gateway-route-table-propagation";
class MyConvertedCode extends TerraformStack {
  constructor(scope: Construct, name: string) {
    super(scope, name);
    new Ec2TransitGatewayRouteTablePropagation(this, "example", {
      transitGatewayAttachmentId: Token.asString(
        awsEc2TransitGatewayVpcAttachmentExample.id
      ),
      transitGatewayRouteTableId: Token.asString(
        awsEc2TransitGatewayRouteTableExample.id
      ),
    });
  }
}

```

## Argument Reference

The following arguments are supported:

* `transitGatewayAttachmentId` - (Required) Identifier of EC2 Transit Gateway Attachment.
* `transitGatewayRouteTableId` - (Required) Identifier of EC2 Transit Gateway Route Table.

## Attributes Reference

In addition to all arguments above, the following attributes are exported:

* `id` - EC2 Transit Gateway Route Table identifier combined with EC2 Transit Gateway Attachment identifier
* `resourceId` - Identifier of the resource
* `resourceType` - Type of the resource

## Import

`awsEc2TransitGatewayRouteTablePropagation` can be imported by using the EC2 Transit Gateway Route Table identifier, an underscore, and the EC2 Transit Gateway Attachment identifier, e.g.,

```
$ terraform import aws_ec2_transit_gateway_route_table_propagation.example tgw-rtb-12345678_tgw-attach-87654321
```

<!-- cache-key: cdktf-0.17.1 input-3f7fc604735b965a0bdab490984fe7efcec8e99742613ec9237376463dd81611 -->