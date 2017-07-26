[ :ref:`aws <cli:aws>` . :ref:`cloudhsm <cli:aws cloudhsm>` ]

.. _cli:aws cloudhsm describe-hapg:


*************
describe-hapg
*************



===========
Description
===========



Retrieves information about a high-availability partition group.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudhsm-2014-05-30/DescribeHapg>`_


========
Synopsis
========

::

    describe-hapg
  --hapg-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--hapg-arn`` (string)


  The ARN of the high-availability partition group to describe.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

  

  

