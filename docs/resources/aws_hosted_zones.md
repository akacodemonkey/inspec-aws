---
title: About the aws_hosted_zones Resource
platform: aws
---

# aws\_hosted\_zones

Use the `aws_hosted_zones` resource to test the hosted zones configuration.

## Syntax

    describe aws_hosted_zones do
      its('names') { should include ("carry-on.films.com") }
    end
    
#### Parameters

This resource does not expect any parameters.


## Properties

|Property              | Description|
| ---                  | --- |
|name                  | The name of the hosted zone. |
|id                    | It's id. |

## Examples


##### Ensure a specific hosted zone exists
    describe aws_hosted_zones do
      its('names') { should include ("carry-on.films.com") }
    end


## Matchers

This InSpec audit resource has the following special matchers. For a full list of available matchers, please visit our [matchers page](https://www.inspec.io/docs/reference/matchers/).

#### exist

The control will pass if the describe returns at least one result.

Use `should_not` to test the entity should not exist.

    describe aws_eks_clusters.where( <property>: <value>) do
      it { should exist }
    end
      
    describe aws_eks_clusters.where( <property>: <value>) do
      it { should_not exist }
    end
    

## AWS Permissions

Your [Principal](https://docs.aws.amazon.com/IAM/latest/UserGuide/intro-structure.html#intro-structure-principal) will need the `route53:ListHostedZones` action with Effect set to Allow.

You can find detailed documentation at [Amazon Route 53](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/r53-api-permissions-ref.html)