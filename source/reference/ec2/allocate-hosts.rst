[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 allocate-hosts:


**************
allocate-hosts
**************



===========
Description
===========



Allocates a Dedicated host to your account. At minimum you need to specify the instance size type, Availability Zone, and quantity of hosts you want to allocate.



========
Synopsis
========

::

    allocate-hosts
  [--auto-placement <value>]
  [--client-token <value>]
  --instance-type <value>
  --quantity <value>
  --availability-zone <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--auto-placement`` (string)


  This is enabled by default. This property allows instances to be automatically placed onto available Dedicated hosts, when you are launching instances without specifying a host ID.

   

  Default: Enabled

  

  Possible values:

  
  *   ``on``

  
  *   ``off``

  

  

``--client-token`` (string)


  Unique, case-sensitive identifier you provide to ensure idempotency of the request. For more information, see `How to Ensure Idempotency`_ in the *Amazon Elastic Compute Cloud User Guide* . 

  

``--instance-type`` (string)


  Specify the instance type that you want your Dedicated hosts to be configured for. When you specify the instance type, that is the only instance type that you can launch onto that host.

  

``--quantity`` (integer)


  The number of Dedicated hosts you want to allocate to your account with these parameters.

  

``--availability-zone`` (string)


  The Availability Zone for the Dedicated hosts.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To allocate a Dedicated host to your account**

This example allocates a single Dedicated host in a specific Availability Zone, onto which you can launch m3.medium instances, to your account. 

Command::

    aws ec2 allocate-hosts --instance-type m3.medium --availability-zone us-east-1b --quantity 1

Output::

  {
      "HostIds": [
      "h-029e7409a337631f"
      ]
  }




======
Output
======

HostIds -> (list)

  

  The ID of the allocated Dedicated host. This is used when you want to launch an instance onto a specific host.

  

  (string)

    

    

  



.. _How to Ensure Idempotency: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Run_Instance_Idempotency.html
