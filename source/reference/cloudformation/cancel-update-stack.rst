[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation cancel-update-stack:


*******************
cancel-update-stack
*******************



===========
Description
===========



Cancels an update on the specified stack. If the call completes successfully, the stack rolls back the update and reverts to the previous stack configuration.

 

.. note::

   

  You can cancel only stacks that are in the UPDATE_IN_PROGRESS state.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudformation-2010-05-15/CancelUpdateStack>`_


========
Synopsis
========

::

    cancel-update-stack
  --stack-name <value>
  [--client-request-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stack-name`` (string)


  The name or the unique stack ID that is associated with the stack.

  

``--client-request-token`` (string)


  A unique identifier for this ``cancel-update-stack`` request. Specify this token if you plan to retry requests so that AWS CloudFormation knows that you're not attempting to cancel an update on a stack with the same name. You might retry ``cancel-update-stack`` requests to ensure that AWS CloudFormation successfully received them.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To cancel a stack update that is in progress**

The following ``cancel-update-stack`` command cancels a stack update on the ``myteststack`` stack::

  aws cloudformation cancel-update-stack --stack-name myteststack


======
Output
======

None