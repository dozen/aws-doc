[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-internet-gateways:


**************************
describe-internet-gateways
**************************



===========
Description
===========



Describes one or more of your Internet gateways.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeInternetGateways>`_


========
Synopsis
========

::

    describe-internet-gateways
  [--filters <value>]
  [--dry-run | --no-dry-run]
  [--internet-gateway-ids <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filters`` (list)


  One or more filters.

   

   
  * ``attachment.state`` - The current state of the attachment between the gateway and the VPC (``available`` ). Present only if a VPC is attached. 
   
  * ``attachment.vpc-id`` - The ID of an attached VPC. 
   
  * ``internet-gateway-id`` - The ID of the Internet gateway. 
   
  * ``tag`` :*key* =*value* - The key/value combination of a tag assigned to the resource. Specify the key of the tag in the filter name and the value of the tag in the filter value. For example, for the tag Purpose=X, specify ``tag:Purpose`` for the filter name and ``X`` for the filter value. 
   
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



``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--internet-gateway-ids`` (list)


  One or more Internet gateway IDs.

   

  Default: Describes all your Internet gateways.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe your Internet gateways**

This example describes your Internet gateways.

Command::

  aws ec2 describe-internet-gateways

Output::

  {
      "InternetGateways": [
          {
              "Tags": [],
              "InternetGatewayId": "igw-c0a643a9",
              "Attachments": [
                  {
                      "State": "available",
                      "VpcId": "vpc-a01106c2"
                  }
              ]
          },
          {
              "Tags": [],
              "InternetGatewayId": "igw-046d7966",
              "Attachments": []
          }
      ]  
  }
  
**To describe the Internet gateway for a specific VPC**

This example describes the Internet gateway for the specified VPC.

Command::

  aws ec2 describe-internet-gateways --filters "Name=attachment.vpc-id,Values=vpc-a01106c2"

Output::

  {
      "InternetGateways": [
          {
              "Tags": [],
              "InternetGatewayId": "igw-c0a643a9",
              "Attachments": [
                  {
                      "State": "available",
                      "VpcId": "vpc-a01106c2"
                  }
              ]
          }
      ]  
  }


======
Output
======

InternetGateways -> (list)

  

  Information about one or more Internet gateways.

  

  (structure)

    

    Describes an Internet gateway.

    

    Attachments -> (list)

      

      Any VPCs attached to the Internet gateway.

      

      (structure)

        

        Describes the attachment of a VPC to an Internet gateway or an egress-only Internet gateway.

        

        State -> (string)

          

          The current state of the attachment.

          

          

        VpcId -> (string)

          

          The ID of the VPC.

          

          

        

      

    InternetGatewayId -> (string)

      

      The ID of the Internet gateway.

      

      

    Tags -> (list)

      

      Any tags assigned to the Internet gateway.

      

      (structure)

        

        Describes a tag.

        

        Key -> (string)

          

          The key of the tag.

           

          Constraints: Tag keys are case-sensitive and accept a maximum of 127 Unicode characters. May not begin with ``aws:``  

          

          

        Value -> (string)

          

          The value of the tag.

           

          Constraints: Tag values are case-sensitive and accept a maximum of 255 Unicode characters.

          

          

        

      

    

  

