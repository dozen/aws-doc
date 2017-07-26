[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-vpc-classic-link-dns-support:


*************************************
describe-vpc-classic-link-dns-support
*************************************



===========
Description
===========



Describes the ClassicLink DNS support status of one or more VPCs. If enabled, the DNS hostname of a linked EC2-Classic instance resolves to its private IP address when addressed from an instance in the VPC to which it's linked. Similarly, the DNS hostname of an instance in a VPC resolves to its private IP address when addressed from a linked EC2-Classic instance. For more information about ClassicLink, see `ClassicLink`_ in the Amazon Elastic Compute Cloud User Guide.



========
Synopsis
========

::

    describe-vpc-classic-link-dns-support
  [--vpc-ids <value>]
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--vpc-ids`` (list)


  One or more VPC IDs.

  



Syntax::

  "string" "string" ...



``--max-results`` (integer)


  The maximum number of items to return for this request. The request returns a token that you can specify in a subsequent call to get the next set of results.

  

``--next-token`` (string)


  The token for the next set of items to return. (You received this token from a prior call.)

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe ClassicLink DNS support for your VPCs**

This example describes the ClassicLink DNS support status of all of your VPCs. 

Command::

  aws ec2 describe-vpc-classic-link-dns-support

Output::

  {
    "Vpcs": [
      {
        "VpcId": "vpc-88888888", 
        "ClassicLinkDnsSupported": true
      }, 
      {
        "VpcId": "vpc-1a2b3c4d", 
        "ClassicLinkDnsSupported": false
      }
    ]
  }

======
Output
======

Vpcs -> (list)

  

  Information about the ClassicLink DNS support status of the VPCs.

  

  (structure)

    

    Describes the ClassicLink DNS support status of a VPC.

    

    VpcId -> (string)

      

      The ID of the VPC.

      

      

    ClassicLinkDnsSupported -> (boolean)

      

      Indicates whether ClassicLink DNS support is enabled for the VPC.

      

      

    

  

NextToken -> (string)

  

  The token to use when requesting the next set of items.

  

  



.. _ClassicLink: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/vpc-classiclink.html
