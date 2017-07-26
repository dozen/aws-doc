[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 enable-vpc-classic-link:


***********************
enable-vpc-classic-link
***********************



===========
Description
===========



Enables a VPC for ClassicLink. You can then link EC2-Classic instances to your ClassicLink-enabled VPC to allow communication over private IP addresses. You cannot enable your VPC for ClassicLink if any of your VPC's route tables have existing routes for address ranges within the ``10.0.0.0/8`` IP address range, excluding local routes for VPCs in the ``10.0.0.0/16`` and ``10.1.0.0/16`` IP address ranges. For more information, see `ClassicLink`_ in the Amazon Elastic Compute Cloud User Guide.



========
Synopsis
========

::

    enable-vpc-classic-link
  [--dry-run | --no-dry-run]
  --vpc-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--vpc-id`` (string)


  The ID of the VPC.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To enable a VPC for ClassicLink**

This example enables vpc-8888888 for ClassicLink.

Command::

  aws ec2 enable-vpc-classic-link --vpc-id vpc-88888888

Output::

  {
    "Return": true
  }

======
Output
======

Return -> (boolean)

  

  Returns ``true`` if the request succeeds; otherwise, it returns an error.

  

  



.. _ClassicLink: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/vpc-classiclink.html
