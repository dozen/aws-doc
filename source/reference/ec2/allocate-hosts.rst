[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 allocate-hosts:


**************
allocate-hosts
**************



===========
Description
===========



Allocates a Dedicated Host to your account. At minimum you need to specify the instance size type, Availability Zone, and quantity of hosts you want to allocate.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/AllocateHosts>`_


========
Synopsis
========

::

    allocate-hosts
  [--auto-placement <value>]
  --availability-zone <value>
  [--client-token <value>]
  --instance-type <value>
  --quantity <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--auto-placement`` (string)


  This is enabled by default. This property allows instances to be automatically placed onto available Dedicated Hosts, when you are launching instances without specifying a host ID.

   

  Default: Enabled

  

  Possible values:

  
  *   ``on``

  
  *   ``off``

  

  

``--availability-zone`` (string)


  The Availability Zone for the Dedicated Hosts.

  

``--client-token`` (string)


  Unique, case-sensitive identifier you provide to ensure idempotency of the request. For more information, see `How to Ensure Idempotency <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Run_Instance_Idempotency.html>`_ in the *Amazon Elastic Compute Cloud User Guide* . 

  

``--instance-type`` (string)


  Specify the instance type that you want your Dedicated Hosts to be configured for. When you specify the instance type, that is the only instance type that you can launch onto that host.

  

``--quantity`` (integer)


  The number of Dedicated Hosts you want to allocate to your account with these parameters.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

  

  The ID of the allocated Dedicated Host. This is used when you want to launch an instance onto a specific host.

  

  (string)

    

    

  

