[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation list-change-sets:


****************
list-change-sets
****************



===========
Description
===========



Returns the ID and status of each active change set for a stack. For example, AWS CloudFormation lists change sets that are in the ``CREATE_IN_PROGRESS`` or ``CREATE_PENDING`` state.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudformation-2010-05-15/ListChangeSets>`_


========
Synopsis
========

::

    list-change-sets
  --stack-name <value>
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stack-name`` (string)


  The name or the Amazon Resource Name (ARN) of the stack for which you want to list change sets.

  

``--next-token`` (string)


  A string (provided by the  list-change-sets response output) that identifies the next page of change sets that you want to retrieve.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Summaries -> (list)

  

  A list of ``ChangeSetSummary`` structures that provides the ID and status of each change set for the specified stack.

  

  (structure)

    

    The ``ChangeSetSummary`` structure describes a change set, its status, and the stack with which it's associated.

    

    StackId -> (string)

      

      The ID of the stack with which the change set is associated.

      

      

    StackName -> (string)

      

      The name of the stack with which the change set is associated.

      

      

    ChangeSetId -> (string)

      

      The ID of the change set.

      

      

    ChangeSetName -> (string)

      

      The name of the change set.

      

      

    ExecutionStatus -> (string)

      

      If the change set execution status is ``AVAILABLE`` , you can execute the change set. If you can’t execute the change set, the status indicates why. For example, a change set might be in an ``UNAVAILABLE`` state because AWS CloudFormation is still creating it or in an ``OBSOLETE`` state because the stack was already updated.

      

      

    Status -> (string)

      

      The state of the change set, such as ``CREATE_IN_PROGRESS`` , ``CREATE_COMPLETE`` , or ``FAILED`` .

      

      

    StatusReason -> (string)

      

      A description of the change set's status. For example, if your change set is in the ``FAILED`` state, AWS CloudFormation shows the error message.

      

      

    CreationTime -> (timestamp)

      

      The start time when the change set was created, in UTC.

      

      

    Description -> (string)

      

      Descriptive information about the change set.

      

      

    

  

NextToken -> (string)

  

  If the output exceeds 1 MB, a string that identifies the next page of change sets. If there is no additional page, this value is null.

  

  

