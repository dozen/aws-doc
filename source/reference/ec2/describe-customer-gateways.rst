[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-customer-gateways:


**************************
describe-customer-gateways
**************************



===========
Description
===========



Describes one or more of your VPN customer gateways.

 

For more information about VPN customer gateways, see `Adding a Hardware Virtual Private Gateway to Your VPC`_ in the *Amazon Virtual Private Cloud User Guide* .



========
Synopsis
========

::

    describe-customer-gateways
  [--dry-run | --no-dry-run]
  [--customer-gateway-ids <value>]
  [--filters <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--customer-gateway-ids`` (list)


  One or more customer gateway IDs.

   

  Default: Describes all your customer gateways.

  



Syntax::

  "string" "string" ...



``--filters`` (list)


  One or more filters.

   

   
  * ``bgp-asn`` - The customer gateway's Border Gateway Protocol (BGP) Autonomous System Number (ASN). 
   
  * ``customer-gateway-id`` - The ID of the customer gateway. 
   
  * ``ip-address`` - The IP address of the customer gateway's Internet-routable external interface. 
   
  * ``state`` - The state of the customer gateway (``pending`` | ``available`` | ``deleting`` | ``deleted`` ). 
   
  * ``type`` - The type of customer gateway. Currently, the only supported type is ``ipsec.1`` . 
   
  * ``tag`` :*key* =*value* - The key/value combination of a tag assigned to the resource. 
   
  * ``tag-key`` - The key of a tag assigned to the resource. This filter is independent of the ``tag-value`` filter. For example, if you use both the filter "tag-key=Purpose" and the filter "tag-value=X", you get any resources assigned both the tag key Purpose (regardless of what the tag's value is), and the tag value X (regardless of what the tag's key is). If you want to list only resources where Purpose is X, see the ``tag`` :*key* =*value* filter. 
   
  * ``tag-value`` - The value of a tag assigned to the resource. This filter is independent of the ``tag-key`` filter. 
   

  



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



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe your customer gateways**

This example describes your customer gateways.

Command::

  aws ec2 describe-customer-gateways 

Output::

  {
      "CustomerGateways": [
          {
              "CustomerGatewayId": "cgw-b4dc3961",
              "IpAddress": "203.0.113.12",
              "State": "available",
              "Type": "ipsec.1",
              "BgpAsn": "65000"
          },
          {
              "CustomerGatewayId": "cgw-0e11f167",
              "IpAddress": "12.1.2.3",
              "State": "available",
              "Type": "ipsec.1",
              "BgpAsn": "65534"
          }
      ]  
  }
  
**To describe a specific customer gateway**

This example describes the specified customer gateway.

Command::

  aws ec2 describe-customer-gateways --customer-gateway-ids cgw-0e11f167

Output::

  {
      "CustomerGateways": [
          {
              "CustomerGatewayId": "cgw-0e11f167",
              "IpAddress": "12.1.2.3",
              "State": "available",
              "Type": "ipsec.1",
              "BgpAsn": "65534"
          }
      ]  
  }  

======
Output
======

CustomerGateways -> (list)

  

  Information about one or more customer gateways.

  

  (structure)

    

    Describes a customer gateway.

    

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
