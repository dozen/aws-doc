[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-vpc-endpoints:


**********************
describe-vpc-endpoints
**********************



===========
Description
===========



Describes one or more of your VPC endpoints.



========
Synopsis
========

::

    describe-vpc-endpoints
  [--dry-run | --no-dry-run]
  [--vpc-endpoint-ids <value>]
  [--filters <value>]
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--vpc-endpoint-ids`` (list)


  One or more endpoint IDs.

  



Syntax::

  "string" "string" ...



``--filters`` (list)


  One or more filters.

   

   
  * ``service-name`` : The name of the AWS service. 
   
  * ``vpc-id`` : The ID of the VPC in which the endpoint resides. 
   
  * ``vpc-endpoint-id`` : The ID of the endpoint. 
   
  * ``vpc-endpoint-state`` : The state of the endpoint. (``pending`` | ``available`` | ``deleting`` | ``deleted`` ) 
   

  



Shorthand Syntax::

    Name=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Values": ["string", ...]
    }
    ...
  ]



``--max-results`` (integer)


  The maximum number of items to return for this request. The request returns a token that you can specify in a subsequent call to get the next set of results.

   

  Constraint: If the value is greater than 1000, we return only 1000 items.

  

``--next-token`` (string)


  The token for the next set of items to return. (You received this token from a prior call.)

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe endpoints**

This example describes all of your endpoints.

Command::

  aws ec2 describe-vpc-endpoints

Output::

  {
    "VpcEndpoints": [
      {
        "PolicyDocument": "{\"Version\":\"2008-10-17\",\"Statement\":[{\"Sid\":\"\",\"Effect\":\"Allow\",\"Principal\":\"*\",\"Action\":\"*\",\"Resource\":\"*\"}]}", 
        "VpcId": "vpc-ec43eb89", 
        "State": "available", 
        "ServiceName": "com.amazonaws.us-east-1.s3", 
        "RouteTableIds": [
          "rtb-4e5ef02b"
        ], 
        "VpcEndpointId": "vpce-3ecf2a57", 
        "CreationTimestamp": "2015-05-15T09:40:50Z"
      }
    ]
  } 

======
Output
======

VpcEndpoints -> (list)

  

  Information about the endpoints.

  

  (structure)

    

    Describes a VPC endpoint.

    

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

      

      

    

  

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  

