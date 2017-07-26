[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation delete-change-set:


*****************
delete-change-set
*****************



===========
Description
===========



Deletes the specified change set. Deleting change sets ensures that no one executes the wrong change set.

 

If the call successfully completes, AWS CloudFormation successfully deleted the change set.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudformation-2010-05-15/DeleteChangeSet>`_


========
Synopsis
========

::

    delete-change-set
  --change-set-name <value>
  [--stack-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--change-set-name`` (string)


  The name or Amazon Resource Name (ARN) of the change set that you want to delete.

  

``--stack-name`` (string)


  If you specified the name of a change set to delete, specify the stack name or ID (ARN) that is associated with it.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

