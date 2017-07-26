[ :ref:`aws <cli:aws>` . :ref:`cloudhsm <cli:aws cloudhsm>` ]

.. _cli:aws cloudhsm describe-hapg:


*************
describe-hapg
*************



===========
Description
===========



Retrieves information about a high-availability partition group.



========
Synopsis
========

::

    describe-hapg
  --hapg-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--hapg-arn`` (string)


  The ARN of the high-availability partition group to describe.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

HapgArn -> (string)

  

  The ARN of the high-availability partition group.

  

  

HapgSerial -> (string)

  

  The serial number of the high-availability partition group.

  

  

HsmsLastActionFailed -> (list)

  

  Contains a list of ARNs that identify the HSMs.

  

  (string)

    

    An ARN that identifies an HSM.

    

    

  

HsmsPendingDeletion -> (list)

  

  Contains a list of ARNs that identify the HSMs.

  

  (string)

    

    An ARN that identifies an HSM.

    

    

  

HsmsPendingRegistration -> (list)

  

  Contains a list of ARNs that identify the HSMs.

  

  (string)

    

    An ARN that identifies an HSM.

    

    

  

Label -> (string)

  

  The label for the high-availability partition group.

  

  

LastModifiedTimestamp -> (string)

  

  The date and time the high-availability partition group was last modified.

  

  

PartitionSerialList -> (list)

  

  The list of partition serial numbers that belong to the high-availability partition group.

  

  (string)

    

    

  

State -> (string)

  

  The state of the high-availability partition group.

  

  

