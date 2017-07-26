[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 modify-vpc-attribute:


********************
modify-vpc-attribute
********************



===========
Description
===========



Modifies the specified attribute of the specified VPC.



========
Synopsis
========

::

    modify-vpc-attribute
  --vpc-id <value>
  [--enable-dns-support | --no-enable-dns-support]
  [--enable-dns-hostnames | --no-enable-dns-hostnames]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--vpc-id`` (string)


  The ID of the VPC.

  

``--enable-dns-support`` | ``--no-enable-dns-support`` (structure)


  Indicates whether the DNS resolution is supported for the VPC. If enabled, queries to the Amazon provided DNS server at the 169.254.169.253 IP address, or the reserved IP address at the base of the VPC network range "plus two" will succeed. If disabled, the Amazon provided DNS service in the VPC that resolves public DNS hostnames to IP addresses is not enabled. 

   

  You cannot modify the DNS resolution and DNS hostnames attributes in the same request. Use separate requests for each attribute.

  

``--enable-dns-hostnames`` | ``--no-enable-dns-hostnames`` (structure)


  Indicates whether the instances launched in the VPC get DNS hostnames. If enabled, instances in the VPC get DNS hostnames; otherwise, they do not.

   

  You cannot modify the DNS resolution and DNS hostnames attributes in the same request. Use separate requests for each attribute. You can only enable DNS hostnames if you've enabled DNS support.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To modify the enableDnsSupport attribute**

This example modifies the ``enableDnsSupport`` attribute. This attribute indicates whether DNS resolution is enabled for the VPC. If this attribute is ``true``, the Amazon DNS server resolves DNS hostnames for your instances to their corresponding IP addresses; otherwise, it does not. If the command succeeds, no output is returned.

Command::

  aws ec2 modify-vpc-attribute --vpc-id vpc-a01106c2 --enable-dns-support "{\"Value\":false}"
  
**To modify the enableDnsHostnames attribute**

This example modifies the ``enableDnsHostnames`` attribute. This attribute indicates whether instances launched in the VPC get DNS hostnames. If this attribute is ``true``, instances in the VPC get DNS hostnames; otherwise, they do not. If the command succeeds, no output is returned.

Command::

  aws ec2 modify-vpc-attribute --vpc-id vpc-a01106c2 --enable-dns-hostnames "{\"Value\":false}"


======
Output
======

None