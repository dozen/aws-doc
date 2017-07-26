[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 modify-instance-placement:


*************************
modify-instance-placement
*************************



===========
Description
===========



Set the instance affinity value for a specific stopped instance and modify the instance tenancy setting.

 

Instance affinity is disabled by default. When instance affinity is ``host`` and it is not associated with a specific Dedicated host, the next time it is launched it will automatically be associated with the host it lands on. This relationship will persist if the instance is stopped/started, or rebooted.

 

You can modify the host ID associated with a stopped instance. If a stopped instance has a new host ID association, the instance will target that host when restarted.

 

You can modify the tenancy of a stopped instance with a tenancy of ``host`` or ``dedicated`` .

 

Affinity, hostID, and tenancy are not required parameters, but at least one of them must be specified in the request. affinity and tenancy can be modified in the same request, but tenancy can only be modified on instances that are stopped.



========
Synopsis
========

::

    modify-instance-placement
  --instance-id <value>
  [--tenancy <value>]
  [--affinity <value>]
  [--host-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--instance-id`` (string)


  The ID of the instance that you are modifying.

  

``--tenancy`` (string)


  The tenancy of the instance that you are modifying.

  

  Possible values:

  
  *   ``dedicated``

  
  *   ``host``

  

  

``--affinity`` (string)


  The new affinity setting for the instance.

  

  Possible values:

  
  *   ``default``

  
  *   ``host``

  

  

``--host-id`` (string)


  The ID of the Dedicated host that the instance will have affinity with.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To set the instance affinity value for a specific stopped Dedicated host**

To modify the affinity of an instance so it always has affinity with the specified Dedicated host . 

Command::

  aws ec2 modify-instance-placement --instance-id=i-f0d45a40 --host-id h-029e7409a3350a31f

Output::

  { 
    "Return":  true
   }


======
Output
======

Return -> (boolean)

  

  Is ``true`` if the request succeeds, and an error otherwise.

  

  

