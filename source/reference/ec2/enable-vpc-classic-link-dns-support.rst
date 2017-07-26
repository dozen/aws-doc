[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 enable-vpc-classic-link-dns-support:


***********************************
enable-vpc-classic-link-dns-support
***********************************



===========
Description
===========



Enables a VPC to support DNS hostname resolution for ClassicLink. If enabled, the DNS hostname of a linked EC2-Classic instance resolves to its private IP address when addressed from an instance in the VPC to which it's linked. Similarly, the DNS hostname of an instance in a VPC resolves to its private IP address when addressed from a linked EC2-Classic instance. For more information about ClassicLink, see `ClassicLink`_ in the Amazon Elastic Compute Cloud User Guide.



========
Synopsis
========

::

    enable-vpc-classic-link-dns-support
  [--vpc-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--vpc-id`` (string)


  The ID of the VPC. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To enable ClassicLink DNS support for a VPC**

This example enables ClassicLink DNS support for ``vpc-88888888``.

Command::

  aws ec2 enable-vpc-classic-link-dns-support --vpc-id vpc-88888888

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
