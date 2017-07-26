[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-nat-gateway:


******************
create-nat-gateway
******************



===========
Description
===========



Creates a NAT gateway in the specified subnet. A NAT gateway can be used to enable instances in a private subnet to connect to the Internet. This action creates a network interface in the specified subnet with a private IP address from the IP address range of the subnet. For more information, see `NAT Gateways`_ in the *Amazon Virtual Private Cloud User Guide* .



========
Synopsis
========

::

    create-nat-gateway
  --subnet-id <value>
  --allocation-id <value>
  [--client-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--subnet-id`` (string)


  The subnet in which to create the NAT gateway.

  

``--allocation-id`` (string)


  The allocation ID of an Elastic IP address to associate with the NAT gateway. If the Elastic IP address is associated with another resource, you must first disassociate it.

  

``--client-token`` (string)


  Unique, case-sensitive identifier you provide to ensure the idempotency of the request. For more information, see `How to Ensure Idempotency`_ .

   

  Constraint: Maximum 64 ASCII characters.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To create a NAT gateway**

This example creates a NAT gateway in subnet ``subnet-1a2b3c4d`` and associates an Elastic IP address with the allocation ID ``eipalloc-37fc1a52`` with the NAT gateway. 

Command::

  aws ec2 create-nat-gateway --subnet-id subnet-1a2b3c4d --allocation-id eipalloc-37fc1a52

Output::

  {
    "NatGateway": {
      "NatGatewayAddresses": [
        {
          "AllocationId": "eipalloc-37fc1a52"
        }
      ], 
      "VpcId": "vpc-1122aabb", 
      "State": "pending", 
      "NatGatewayId": "nat-08d48af2a8e83edfd", 
      "SubnetId": "subnet-1a2b3c4d", 
      "CreateTime": "2015-12-17T12:45:26.732Z"
    }
  }

======
Output
======

NatGateway -> (structure)

  

  Information about the NAT gateway.

  

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
     

    

    

  

ClientToken -> (string)

  

  Unique, case-sensitive identifier to ensure the idempotency of the request. Only returned if a client token was provided in the request.

  

  



.. _NAT Gateways: http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/vpc-nat-gateway.html
.. _How to Ensure Idempotency: http://docs.aws.amazon.com/AWSEC2/latest/APIReference/Run_Instance_Idempotency.html
