[ :ref:`aws <cli:aws>` . :ref:`events <cli:aws events>` ]

.. _cli:aws events remove-targets:


**************
remove-targets
**************



===========
Description
===========



Removes the specified targets from the specified rule. When the rule is triggered, those targets are no longer be invoked.

 

When you remove a target, when the associated rule triggers, removed targets might continue to be invoked. Please allow a short period of time for changes to take effect.

 

This action can partially fail if too many requests are made at the same time. If that happens, ``FailedEntryCount`` is non-zero in the response and each entry in ``FailedEntries`` provides the ID of the failed target and the error code.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/events-2015-10-07/RemoveTargets>`_


========
Synopsis
========

::

    remove-targets
  --rule <value>
  --ids <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rule`` (string)


  The name of the rule.

  

``--ids`` (list)


  The IDs of the targets to remove from the rule.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To remove a target for an event**

This example removes the Amazon Kinesis stream named MyStream1 from being a target of the rule DailyLambdaFunction. When DailyLambdaFunction was created, this stream was set as a target with an ID of Target1::

  aws events remove-targets --rule "DailyLambdaFunction" --ids "Target1"


======
Output
======

FailedEntryCount -> (integer)

  

  The number of failed entries.

  

  

FailedEntries -> (list)

  

  The failed target entries.

  

  (structure)

    

    Represents a target that failed to be removed from a rule.

    

    TargetId -> (string)

      

      The ID of the target.

      

      

    ErrorCode -> (string)

      

      The error code that indicates why the target removal failed. If the value is ``ConcurrentModificationException`` , too many requests were made at the same time.

      

      

    ErrorMessage -> (string)

      

      The error message that explains why the target removal failed.

      

      

    

  

