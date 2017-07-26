[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-vpc-endpoint:


*******************
create-vpc-endpoint
*******************



===========
Description
===========



Creates a VPC endpoint for a specified AWS service. An endpoint enables you to create a private connection between your VPC and another AWS service in your account. You can specify an endpoint policy to attach to the endpoint that will control access to the service from your VPC. You can also specify the VPC route tables that use the endpoint.

 

Use  describe-vpc-endpoint-services to get a list of supported AWS services.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/CreateVpcEndpoint>`_


========
Synopsis
========

::

    create-vpc-endpoint
  [--client-token <value>]
  [--dry-run | --no-dry-run]
  [--policy-document <value>]
  [--route-table-ids <value>]
  --service-name <value>
  --vpc-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--client-token`` (string)


  Unique, case-sensitive identifier you provide to ensure the idempotency of the request. For more information, see `How to Ensure Idempotency <http://docs.aws.amazon.com/AWSEC2/latest/APIReference/Run_Instance_Idempotency.html>`_ .

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--policy-document`` (string)


  A policy to attach to the endpoint that controls access to the service. The policy must be in valid JSON format. If this parameter is not specified, we attach a default policy that allows full access to the service.

  

``--route-table-ids`` (list)


  One or more route table IDs.

  



Syntax::

  "string" "string" ...



``--service-name`` (string)


  The AWS service name, in the form ``com.amazonaws.*region* .*service* `` . To get a list of available services, use the  describe-vpc-endpoint-services request.

  

``--vpc-id`` (string)


  The ID of the VPC in which the endpoint will be used.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

ClientToken -> (string)

  

  Unique, case-sensitive identifier you provide to ensure the idempotency of the request.

  

  

VpcEndpoint -> (structure)

  

  Information about the endpoint.

  

  CreationTimestamp -> (timestamp)

    

    The date and time the VPC endpoint was created.

    

    

  PolicyDocument -> (string)

    

    The policy document associated with the endpoint.

    

    

  RouteTableIds -> (list)

    

    One or more route tables associated with the endpoint.

    

    (string)

      

      

    

  ServiceName -> (string)

    

    The name of the AWS service to which the endpoint is associated.

    

    

  State -> (string)

    

    The state of the VPC endpoint.

    

    

  VpcEndpointId -> (string)

    

    The ID of the VPC endpoint.

    

    

  VpcId -> (string)

    

    The ID of the VPC to which the endpoint is associated.

    

    

  

