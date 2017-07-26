[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 modify-instance-placement:


*************************
modify-instance-placement
*************************



===========
Description
===========



Set the instance affinity value for a specific stopped instance and modify the instance tenancy setting.

 

Instance affinity is disabled by default. When instance affinity is ``host`` and it is not associated with a specific Dedicated Host, the next time it is launched it will automatically be associated with the host it lands on. This relationship will persist if the instance is stopped/started, or rebooted.

 

You can modify the host ID associated with a stopped instance. If a stopped instance has a new host ID association, the instance will target that host when restarted.

 

You can modify the tenancy of a stopped instance with a tenancy of ``host`` or ``dedicated`` .

 

Affinity, hostID, and tenancy are not required parameters, but at least one of them must be specified in the request. affinity and tenancy can be modified in the same request, but tenancy can only be modified on instances that are stopped.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/ModifyInstancePlacement>`_


========
Synopsis
========

::

    modify-instance-placement
  [--affinity <value>]
  [--host-id <value>]
  --instance-id <value>
  [--tenancy <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--affinity`` (string)


  The new affinity setting for the instance.

  

  Possible values:

  
  *   ``default``

  
  *   ``host``

  

  

``--host-id`` (string)


  The ID of the Dedicated Host that the instance will have affinity with.

  

``--instance-id`` (string)


  The ID of the instance that you are modifying.

  

``--tenancy`` (string)


  The tenancy of the instance that you are modifying.

  

  Possible values:

  
  *   ``dedicated``

  
  *   ``host``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To set the instance affinity value for a specific stopped Dedicated Host**

To modify the affinity of an instance so it always has affinity with the specified Dedicated Host . 

Command::

  aws ec2 modify-instance-placement --instance-id=i-1234567890abcdef0 --host-id h-029e7409a3350a31f

Output::

  { 
    "Return":  true
   }


======
Output
======

Return -> (boolean)

  

  Is ``true`` if the request succeeds, and an error otherwise.

  

  

