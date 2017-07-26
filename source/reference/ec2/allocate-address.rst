[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 allocate-address:


****************
allocate-address
****************



===========
Description
===========



Acquires an Elastic IP address.

 

An Elastic IP address is for use either in the EC2-Classic platform or in a VPC. For more information, see `Elastic IP Addresses <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/AllocateAddress>`_


========
Synopsis
========

::

    allocate-address
  [--domain <value>]
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--domain`` (string)


  Set to ``vpc`` to allocate the address for use with instances in a VPC.

   

  Default: The address is for use with instances in EC2-Classic.

  

  Possible values:

  
  *   ``vpc``

  
  *   ``standard``

  

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To allocate an Elastic IP address for EC2-Classic**

This example allocates an Elastic IP address to use with an instance in EC2-Classic.

Command::

  aws ec2 allocate-address

Output::

  {
      "PublicIp": "198.51.100.0",
      "Domain": "standard"
  }

**To allocate an Elastic IP address for EC2-VPC**

This example allocates an Elastic IP address to use with an instance in a VPC.

Command::

  aws ec2 allocate-address --domain vpc

Output::

  {
      "PublicIp": "203.0.113.0",
      "Domain": "vpc",
      "AllocationId": "eipalloc-64d5890a"
  }



======
Output
======

PublicIp -> (string)

  

  The Elastic IP address.

  

  

AllocationId -> (string)

  

  [EC2-VPC] The ID that AWS assigns to represent the allocation of the Elastic IP address for use with instances in a VPC.

  

  

Domain -> (string)

  

  Indicates whether this Elastic IP address is for use with instances in EC2-Classic (``standard`` ) or instances in a VPC (``vpc`` ).

  

  

