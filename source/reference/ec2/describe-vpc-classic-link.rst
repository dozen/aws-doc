[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-vpc-classic-link:


*************************
describe-vpc-classic-link
*************************



===========
Description
===========



Describes the ClassicLink status of one or more VPCs.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeVpcClassicLink>`_


========
Synopsis
========

::

    describe-vpc-classic-link
  [--filters <value>]
  [--dry-run | --no-dry-run]
  [--vpc-ids <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filters`` (list)


  One or more filters.

   

   
  * ``is-classic-link-enabled`` - Whether the VPC is enabled for ClassicLink (``true`` | ``false`` ). 
   
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

  

``--vpc-ids`` (list)


  One or more VPCs for which you want to describe the ClassicLink status.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe the ClassicLink status of your VPCs**

This example lists the ClassicLink status of vpc-88888888.

Command::

  aws ec2 describe-vpc-classic-link --vpc-id vpc-88888888

Output::

  {
    "Vpcs": [
      {
        "ClassicLinkEnabled": true, 
        "VpcId": "vpc-88888888", 
        "Tags": [
          {
            "Value": "classiclinkvpc", 
            "Key": "Name"
          }
        ]
      }
    ]
  }

This example lists only VPCs that are enabled for Classiclink (the filter value of ``is-classic-link-enabled`` is set to ``true``).

Command::

  aws ec2 describe-vpc-classic-link --filter "Name=is-classic-link-enabled,Values=true"


======
Output
======

Vpcs -> (list)

  

  The ClassicLink status of one or more VPCs.

  

  (structure)

    

    Describes whether a VPC is enabled for ClassicLink.

    

    ClassicLinkEnabled -> (boolean)

      

      Indicates whether the VPC is enabled for ClassicLink.

      

      

    Tags -> (list)

      

      Any tags assigned to the VPC.

      

      (structure)

        

        Describes a tag.

        

        Key -> (string)

          

          The key of the tag.

           

          Constraints: Tag keys are case-sensitive and accept a maximum of 127 Unicode characters. May not begin with ``aws:``  

          

          

        Value -> (string)

          

          The value of the tag.

           

          Constraints: Tag values are case-sensitive and accept a maximum of 255 Unicode characters.

          

          

        

      

    VpcId -> (string)

      

      The ID of the VPC.

      

      

    

  

