[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-nat-gateways:


*********************
describe-nat-gateways
*********************



===========
Description
===========



Describes one or more of the your NAT gateways.



========
Synopsis
========

::

    describe-nat-gateways
  [--nat-gateway-ids <value>]
  [--filter <value>]
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--nat-gateway-ids`` (list)


  One or more NAT gateway IDs.

  



Syntax::

  "string" "string" ...



``--filter`` (list)


  One or more filters.

   

   
  * ``nat-gateway-id`` - The ID of the NAT gateway. 
   
  * ``state`` - The state of the NAT gateway (``pending`` | ``failed`` | ``available`` | ``deleting`` | ``deleted`` ). 
   
  * ``subnet-id`` - The ID of the subnet in which the NAT gateway resides. 
   
  * ``vpc-id`` - The ID of the VPC in which the NAT gateway resides. 
   

  



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

   

  Constraint: If the value specified is greater than 1000, we return only 1000 items.

  

``--next-token`` (string)


  The token to retrieve the next page of results.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe your NAT gateways**

This example describes all of your NAT gateways.

Command::

  aws ec2 describe-nat-gateways

Output::

  {
    "NatGateways": [
      {
        "NatGatewayAddresses": [
          {
            "PublicIp": "198.11.222.333", 
            "NetworkInterfaceId": "eni-9dec76cd", 
            "AllocationId": "eipalloc-89c620ec", 
            "PrivateIp": "10.0.0.149"
          }
        ], 
        "VpcId": "vpc-1a2b3c4d", 
        "State": "available", 
        "NatGatewayId": "nat-05dba92075d71c408", 
        "SubnetId": "subnet-847e4dc2", 
        "CreateTime": "2015-12-01T12:26:55.983Z"
      }, 
      {
        "NatGatewayAddresses": [
          {
            "PublicIp": "1.2.3.12", 
            "NetworkInterfaceId": "eni-71ec7621", 
            "AllocationId": "eipalloc-5d42583f", 
            "PrivateIp": "10.0.0.77"
          }
        ], 
        "VpcId": "vpc-11aa22bb", 
        "State": "deleting", 
        "NatGatewayId": "nat-0a93acc57881d4199", 
        "SubnetId": "subnet-7f7e4d39", 
        "DeleteTime": "2015-12-17T12:26:14.564Z", 
        "CreateTime": "2015-12-01T12:09:22.040Z"
      }
    ]
  }

======
Output
======

NatGateways -> (list)

  

  Information about the NAT gateways.

  

  (structure)

    

    Describes a NAT gateway.

    

    VpcId -> (string)

      

      The ID of the VPC in which the NAT gateway is located.

      

      

    SubnetId -> (string)

      

      The ID of the subnet in which the NAT gateway is located.

      

      

    NatGatewayId -> (string)

      

      The ID of the NAT gateway.

      

      

    CreateTime -> (timestamp)

      

      The date and time the NAT gateway was created.

      

      

    DeleteTime -> (timestamp)

      

      The date and time the NAT gateway was deleted, if applicable.

      

      

    NatGatewayAddresses -> (list)

      

      Information about the IP addresses and network interface associated with the NAT gateway.

      

      (structure)

        

        Describes the IP addresses and network interface associated with a NAT gateway.

        

        PublicIp -> (string)

          

          The Elastic IP address associated with the NAT gateway.

          

          

        AllocationId -> (string)

          

          The allocation ID of the Elastic IP address that's associated with the NAT gateway.

          

          

        PrivateIp -> (string)

          

          The private IP address associated with the Elastic IP address.

          

          

        NetworkInterfaceId -> (string)

          

          The ID of the network interface associated with the NAT gateway.

          

          

        

      

    State -> (string)

      

      The state of the NAT gateway.

      

      

    FailureCode -> (string)

      

      If the NAT gateway could not be created, specifies the error code for the failure. (``InsufficientFreeAddressesInSubnet`` | ``Gateway.NotAttached`` | ``InvalidAllocationID.NotFound`` | ``Resource.AlreadyAssociated`` | ``InternalError`` )

      

      

    FailureMessage -> (string)

      

      If the NAT gateway could not be created, specifies the error message for the failure, that corresponds to the error code. 

       

       
      * For InsufficientFreeAddressesInSubnet: ``Subnet has insufficient free addresses to create this NAT gateway`` 
       
      * For Gateway.NotAttached: ``Network vpc-xxxxxxxx has no Internet gateway attached`` 
       
      * For InvalidAllocationID.NotFound: ``Elastic IP address eipalloc-xxxxxxxx could not be associated with this NAT gateway`` 
       
      * For Resource.AlreadyAssociated: ``Elastic IP address eipalloc-xxxxxxxx is already associated`` 
       
      * For InternalError: ``Network interface eni-xxxxxxxx, created and used internally by this NAT gateway is in an invalid state. Please try again.`` 
       

      

      

    

  

NextToken -> (string)

  

  The token to use to retrieve the next page of results. This value is ``null`` when there are no more results to return.

  

  

