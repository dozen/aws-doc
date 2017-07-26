[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-nat-gateway:


******************
create-nat-gateway
******************



===========
Description
===========



Creates a NAT gateway in the specified subnet. A NAT gateway can be used to enable instances in a private subnet to connect to the Internet. This action creates a network interface in the specified subnet with a private IP address from the IP address range of the subnet. For more information, see `NAT Gateways <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/vpc-nat-gateway.html>`_ in the *Amazon Virtual Private Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/CreateNatGateway>`_


========
Synopsis
========

::

    create-nat-gateway
  --allocation-id <value>
  [--client-token <value>]
  --subnet-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--allocation-id`` (string)


  The allocation ID of an Elastic IP address to associate with the NAT gateway. If the Elastic IP address is associated with another resource, you must first disassociate it.

  

``--client-token`` (string)


  Unique, case-sensitive identifier you provide to ensure the idempotency of the request. For more information, see `How to Ensure Idempotency <http://docs.aws.amazon.com/AWSEC2/latest/APIReference/Run_Instance_Idempotency.html>`_ .

   

  Constraint: Maximum 64 ASCII characters.

  

``--subnet-id`` (string)


  The subnet in which to create the NAT gateway.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

ClientToken -> (string)

  

  Unique, case-sensitive identifier to ensure the idempotency of the request. Only returned if a client token was provided in the request.

  

  

NatGateway -> (structure)

  

  Information about the NAT gateway.

  

  CreateTime -> (timestamp)

    

    The date and time the NAT gateway was created.

    

    

  DeleteTime -> (timestamp)

    

    The date and time the NAT gateway was deleted, if applicable.

    

    

  FailureCode -> (string)

    

    If the NAT gateway could not be created, specifies the error code for the failure. (``InsufficientFreeAddressesInSubnet`` | ``Gateway.NotAttached`` | ``InvalidAllocationID.NotFound`` | ``Resource.AlreadyAssociated`` | ``InternalError`` | ``InvalidSubnetID.NotFound`` )

    

    

  FailureMessage -> (string)

    

    If the NAT gateway could not be created, specifies the error message for the failure, that corresponds to the error code.

     

     
    * For InsufficientFreeAddressesInSubnet: "Subnet has insufficient free addresses to create this NAT gateway" 
     
    * For Gateway.NotAttached: "Network vpc-xxxxxxxx has no Internet gateway attached" 
     
    * For InvalidAllocationID.NotFound: "Elastic IP address eipalloc-xxxxxxxx could not be associated with this NAT gateway" 
     
    * For Resource.AlreadyAssociated: "Elastic IP address eipalloc-xxxxxxxx is already associated" 
     
    * For InternalError: "Network interface eni-xxxxxxxx, created and used internally by this NAT gateway is in an invalid state. Please try again." 
     
    * For InvalidSubnetID.NotFound: "The specified subnet subnet-xxxxxxxx does not exist or could not be found." 
     

    

    

  NatGatewayAddresses -> (list)

    

    Information about the IP addresses and network interface associated with the NAT gateway.

    

    (structure)

      

      Describes the IP addresses and network interface associated with a NAT gateway.

      

      AllocationId -> (string)

        

        The allocation ID of the Elastic IP address that's associated with the NAT gateway.

        

        

      NetworkInterfaceId -> (string)

        

        The ID of the network interface associated with the NAT gateway.

        

        

      PrivateIp -> (string)

        

        The private IP address associated with the Elastic IP address.

        

        

      PublicIp -> (string)

        

        The Elastic IP address associated with the NAT gateway.

        

        

      

    

  NatGatewayId -> (string)

    

    The ID of the NAT gateway.

    

    

  ProvisionedBandwidth -> (structure)

    

    Reserved. If you need to sustain traffic greater than the `documented limits <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/vpc-nat-gateway.html>`_ , contact us through the `Support Center <https://console.aws.amazon.com/support/home?>`_ .

    

    ProvisionTime -> (timestamp)

      

      Reserved. If you need to sustain traffic greater than the `documented limits <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/vpc-nat-gateway.html>`_ , contact us through the `Support Center <https://console.aws.amazon.com/support/home?>`_ .

      

      

    Provisioned -> (string)

      

      Reserved. If you need to sustain traffic greater than the `documented limits <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/vpc-nat-gateway.html>`_ , contact us through the `Support Center <https://console.aws.amazon.com/support/home?>`_ .

      

      

    RequestTime -> (timestamp)

      

      Reserved. If you need to sustain traffic greater than the `documented limits <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/vpc-nat-gateway.html>`_ , contact us through the `Support Center <https://console.aws.amazon.com/support/home?>`_ .

      

      

    Requested -> (string)

      

      Reserved. If you need to sustain traffic greater than the `documented limits <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/vpc-nat-gateway.html>`_ , contact us through the `Support Center <https://console.aws.amazon.com/support/home?>`_ .

      

      

    Status -> (string)

      

      Reserved. If you need to sustain traffic greater than the `documented limits <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/vpc-nat-gateway.html>`_ , contact us through the `Support Center <https://console.aws.amazon.com/support/home?>`_ .

      

      

    

  State -> (string)

    

    The state of the NAT gateway.

     

     
    * ``pending`` : The NAT gateway is being created and is not ready to process traffic. 
     
    * ``failed`` : The NAT gateway could not be created. Check the ``failureCode`` and ``failureMessage`` fields for the reason. 
     
    * ``available`` : The NAT gateway is able to process traffic. This status remains until you delete the NAT gateway, and does not indicate the health of the NAT gateway. 
     
    * ``deleting`` : The NAT gateway is in the process of being terminated and may still be processing traffic. 
     
    * ``deleted`` : The NAT gateway has been terminated and is no longer processing traffic. 
     

    

    

  SubnetId -> (string)

    

    The ID of the subnet in which the NAT gateway is located.

    

    

  VpcId -> (string)

    

    The ID of the VPC in which the NAT gateway is located.

    

    

  

