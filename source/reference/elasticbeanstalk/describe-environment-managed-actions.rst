[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk describe-environment-managed-actions:


************************************
describe-environment-managed-actions
************************************



===========
Description
===========



Lists an environment's upcoming and in-progress managed actions.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticbeanstalk-2010-12-01/DescribeEnvironmentManagedActions>`_


========
Synopsis
========

::

    describe-environment-managed-actions
  [--environment-name <value>]
  [--environment-id <value>]
  [--status <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--environment-name`` (string)


  The name of the target environment.

  

``--environment-id`` (string)


  The environment ID of the target environment.

  

``--status`` (string)


  To show only actions with a particular status, specify a status.

  

  Possible values:

  
  *   ``Scheduled``

  
  *   ``Pending``

  
  *   ``Running``

  
  *   ``Unknown``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ManagedActions -> (list)

  

  A list of upcoming and in-progress managed actions.

  

  (structure)

    

    The record of an upcoming or in-progress managed action.

    

    ActionId -> (string)

      

      A unique identifier for the managed action.

      

      

    ActionDescription -> (string)

      

      A description of the managed action.

      

      

    ActionType -> (string)

      

      The type of managed action.

      

      

    Status -> (string)

      

      The status of the managed action. If the action is ``Scheduled`` , you can apply it immediately with  apply-environment-managed-action .

      

      

    WindowStartTime -> (timestamp)

      

      The start time of the maintenance window in which the managed action will execute.

      

      

    

  

