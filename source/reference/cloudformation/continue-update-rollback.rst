[ :ref:`aws <cli:aws>` . :ref:`cloudformation <cli:aws cloudformation>` ]

.. _cli:aws cloudformation continue-update-rollback:


************************
continue-update-rollback
************************



===========
Description
===========



For a specified stack that is in the ``UPDATE_ROLLBACK_FAILED`` state, continues rolling it back to the ``UPDATE_ROLLBACK_COMPLETE`` state. Depending on the cause of the failure, you can manually `fix the error`_ and continue the rollback. By continuing the rollback, you can return your stack to a working state (the ``UPDATE_ROLLBACK_COMPLETE`` state), and then try to update the stack again.

 

A stack goes into the ``UPDATE_ROLLBACK_FAILED`` state when AWS CloudFormation cannot roll back all changes after a failed stack update. For example, you might have a stack that is rolling back to an old database instance that was deleted outside of AWS CloudFormation. Because AWS CloudFormation doesn't know the database was deleted, it assumes that the database instance still exists and attempts to roll back to it, causing the update rollback to fail.



========
Synopsis
========

::

    continue-update-rollback
  --stack-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--stack-name`` (string)


  The name or the unique ID of the stack that you want to continue rolling back.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======



.. _fix the error: http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/troubleshooting.html#troubleshooting-errors-update-rollback-failed
