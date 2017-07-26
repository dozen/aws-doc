[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk apply-environment-managed-action:


********************************
apply-environment-managed-action
********************************



===========
Description
===========



Applies a scheduled managed action immediately. A managed action can be applied only if its status is ``Scheduled`` . Get the status and action ID of a managed action with  describe-environment-managed-actions .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticbeanstalk-2010-12-01/ApplyEnvironmentManagedAction>`_


========
Synopsis
========

::

    apply-environment-managed-action
  [--environment-name <value>]
  [--environment-id <value>]
  --action-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--environment-name`` (string)


  The name of the target environment.

  

``--environment-id`` (string)


  The environment ID of the target environment.

  

``--action-id`` (string)


  The action ID of the scheduled managed action to execute.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ActionId -> (string)

  

  The action ID of the managed action.

  

  

ActionDescription -> (string)

  

  A description of the managed action.

  

  

ActionType -> (string)

  

  The type of managed action.

  

  

Status -> (string)

  

  The status of the managed action.

  

  

