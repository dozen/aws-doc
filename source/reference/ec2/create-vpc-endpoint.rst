[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-vpc-endpoint:


*******************
create-vpc-endpoint
*******************



===========
Description
===========



Creates a VPC endpoint for a specified AWS service. An endpoint enables you to create a private connection between your VPC and another AWS service in your account. You can specify an endpoint policy to attach to the endpoint that will control access to the service from your VPC. You can also specify the VPC route tables that use the endpoint.

 

Currently, only endpoints to Amazon S3 are supported.



========
Synopsis
========

::

    create-vpc-endpoint
  [--dry-run | --no-dry-run]
  --vpc-id <value>
  --service-name <value>
  [--policy-document <value>]
  [--route-table-ids <value>]
  [--client-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--vpc-id`` (string)


  The ID of the VPC in which the endpoint will be used.

  

``--service-name`` (string)


  The AWS service name, in the form ``com.amazonaws.*region* .*service*`` . To get a list of available services, use the  describe-vpc-endpoint-services request.

  

``--policy-document`` (string)


  A policy to attach to the endpoint that controls access to the service. The policy must be in valid JSON format. If this parameter is not specified, we attach a default policy that allows full access to the service. 

  

``--route-table-ids`` (list)


  One or more route table IDs.

  



Syntax::

  "string" "string" ...



``--client-token`` (string)


  Unique, case-sensitive identifier you provide to ensure the idempotency of the request. For more information, see `How to Ensure Idempotency`_ .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To create an endpoint**

This example creates a VPC endpoint between VPC vpc-1a2b3c4d and Amazon S3 in the us-east-1 region, and associates route table rtb-11aa22bb with the endpoint.

Command::

  aws ec2 create-vpc-endpoint --vpc-id vpc-1a2b3c4d --service-name com.amazonaws.us-east-1.s3 --route-table-ids rtb-11aa22bb

Output::

  {
    "VpcEndpoint": {
    "PolicyDocument": "{\"Version\":\"2008-10-17\",\"Statement\":[{\"Sid\":\"\",\"Effect\":\"Allow\",\"Principal\":\"*\",\"Action\":\"*\",\"Resource\":\"*\"}]}", 
    "VpcId": "vpc-1a2b3c4d", 
    "State": "available", 
    "ServiceName": "com.amazonaws.us-east-1.s3", 
    "RouteTableIds": [
      "rtb-11aa22bb"
    ], 
    "VpcEndpointId": "vpce-3ecf2a57", 
    "CreationTimestamp": "2015-05-15T09:40:50Z"
    }
  }

======
Output
======

VpcEndpoint -> (structure)

  

  Information about the endpoint.

  

  VpcEndpointId -> (string)

    

    The ID of the VPC endpoint.

    

    

  VpcId -> (string)

    

    The ID of the VPC to which the endpoint is associated.

    

    

  ServiceName -> (string)

    

    The name of the AWS service to which the endpoint is associated.

    

    

  State -> (string)

    

    The state of the VPC endpoint.

    

    

  PolicyDocument -> (string)

    

    The policy document associated with the endpoint.

    

    

  RouteTableIds -> (list)

    

    One or more route tables associated with the endpoint.

    

    (string)

      

      

    

  CreationTimestamp -> (timestamp)

    

    The date and time the VPC endpoint was created.

    

    

  

ClientToken -> (string)

  

  Unique, case-sensitive identifier you provide to ensure the idempotency of the request.

  

  



.. _How to Ensure Idempotency: http://docs.aws.amazon.com/AWSEC2/latest/APIReference/Run_Instance_Idempotency.html
