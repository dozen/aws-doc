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



========
Synopsis
========

::

    cancel-update-stack
  --stack-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--stack-name`` (string)


  The name or the unique stack ID that is associated with the stack.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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