[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-customer-gateway:


***********************
create-customer-gateway
***********************



===========
Description
===========



Provides information to AWS about your VPN customer gateway device. The customer gateway is the appliance at your end of the VPN connection. (The device on the AWS side of the VPN connection is the virtual private gateway.) You must provide the Internet-routable IP address of the customer gateway's external interface. The IP address must be static and may be behind a device performing network address translation (NAT).

 

For devices that use Border Gateway Protocol (BGP), you can also provide the device's BGP Autonomous System Number (ASN). You can use an existing ASN assigned to your network. If you don't have an ASN already, you can use a private ASN (in the 64512 - 65534 range).

 

.. note::

   

  Amazon EC2 supports all 2-byte ASN numbers in the range of 1 - 65534, with the exception of 7224, which is reserved in the ``us-east-1`` region, and 9059, which is reserved in the ``eu-west-1`` region.

   

 

For more information about VPN customer gateways, see `Adding a Hardware Virtual Private Gateway to Your VPC`_ in the *Amazon Virtual Private Cloud User Guide* .

 

.. warning::

   

  You cannot create more than one customer gateway with the same VPN type, IP address, and BGP ASN parameter values. If you run an identical request more than one time, the first request creates the customer gateway, and subsequent requests return information about the existing customer gateway. The subsequent requests do not create new customer gateway resources. 

   



========
Synopsis
========

::

    create-customer-gateway
  [--dry-run | --no-dry-run]
  --type <value>
  --public-ip <value>
  --bgp-asn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--type`` (string)


  The type of VPN connection that this customer gateway supports (``ipsec.1`` ).

  

  Possible values:

  
  *   ``ipsec.1``

  

  

``--public-ip`` (string)


  The Internet-routable IP address for the customer gateway's outside interface. The address must be static.

  

``--bgp-asn`` (integer)


  For devices that support BGP, the customer gateway's BGP ASN.

   

  Default: 65000

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To create a customer gateway**

This example creates a customer gateway with the specified IP address for its outside interface.

Command::

  aws ec2 create-customer-gateway --type ipsec.1 --public-ip 12.1.2.3 --bgp-asn 65534

Output::

  {
      "CustomerGateway": {
          "CustomerGatewayId": "cgw-0e11f167",
          "IpAddress": "12.1.2.3",
          "State": "available",
          "Type": "ipsec.1",
          "BgpAsn": "65534"
      }  
  }

======
Output
======

CustomerGateway -> (structure)

  

  Information about the customer gateway.

  

  CustomerGatewayId -> (string)

    

    The ID of the customer gateway.

    

    

  State -> (string)

    

    The current state of the customer gateway (``pending | available | deleting | deleted`` ).

    

    

  Type -> (string)

    

    The type of VPN connection the customer gateway supports (``ipsec.1`` ).

    

    

  IpAddress -> (string)

    

    The Internet-routable IP address of the customer gateway's outside interface.

    

    

  BgpAsn -> (string)

    

    The customer gateway's Border Gateway Protocol (BGP) Autonomous System Number (ASN).

    

    

  Tags -> (list)

    

    Any tags assigned to the customer gateway.

    

    (structure)

      

      Describes a tag.

      

      Key -> (string)

        

        The key of the tag. 

         

        Constraints: Tag keys are case-sensitive and accept a maximum of 127 Unicode characters. May not begin with ``aws:`` 

        

        

      Value -> (string)

        

        The value of the tag.

         

        Constraints: Tag values are case-sensitive and accept a maximum of 255 Unicode characters.

        

        

      

    

  



.. _Adding a Hardware Virtual Private Gateway to Your VPC: http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_VPN.html
