[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` . :ref:`wait <cli:aws ec2 wait>` ]

.. _cli:aws ec2 wait vpc-peering-connection-exists:


*****************************
vpc-peering-connection-exists
*****************************



===========
Description
===========

Wait until 200 response is received when polling with ``describe-vpc-peering-connections``. It will poll every 15 seconds until a successful state has been reached. This will exit with a return code of 255 after 40 failed checks.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeVpcPeeringConnections>`_


========
Synopsis
========

::

    vpc-peering-connection-exists
  [--filters <value>]
  [--dry-run | --no-dry-run]
  [--vpc-peering-connection-ids <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filters`` (list)


  One or more filters.

   

   
  * ``accepter-vpc-info.cidr-block`` - The IPv4 CIDR block of the peer VPC. 
   
  * ``accepter-vpc-info.owner-id`` - The AWS account ID of the owner of the peer VPC. 
   
  * ``accepter-vpc-info.vpc-id`` - The ID of the peer VPC. 
   
  * ``expiration-time`` - The expiration date and time for the VPC peering connection. 
   
  * ``requester-vpc-info.cidr-block`` - The IPv4 CIDR block of the requester's VPC. 
   
  * ``requester-vpc-info.owner-id`` - The AWS account ID of the owner of the requester VPC. 
   
  * ``requester-vpc-info.vpc-id`` - The ID of the requester VPC. 
   
  * ``status-code`` - The status of the VPC peering connection (``pending-acceptance`` | ``failed`` | ``expired`` | ``provisioning`` | ``active`` | ``deleted`` | ``rejected`` ). 
   
  * ``status-message`` - A message that provides more information about the status of the VPC peering connection, if applicable. 
   
  * ``tag`` :*key* =*value* - The key/value combination of a tag assigned to the resource. Specify the key of the tag in the filter name and the value of the tag in the filter value. For example, for the tag Purpose=X, specify ``tag:Purpose`` for the filter name and ``X`` for the filter value. 
   
  * ``tag-key`` - The key of a tag assigned to the resource. This filter is independent of the ``tag-value`` filter. For example, if you use both the filter "tag-key=Purpose" and the filter "tag-value=X", you get any resources assigned both the tag key Purpose (regardless of what the tag's value is), and the tag value X (regardless of what the tag's key is). If you want to list only resources where Purpose is X, see the ``tag`` :*key* =*value* filter. 
   
  * ``tag-value`` - The value of a tag assigned to the resource. This filter is independent of the ``tag-key`` filter. 
   
  * ``vpc-peering-connection-id`` - The ID of the VPC peering connection. 
   

  



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

  

``--vpc-peering-connection-ids`` (list)


  One or more VPC peering connection IDs.

   

  Default: Describes all your VPC peering connections.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None