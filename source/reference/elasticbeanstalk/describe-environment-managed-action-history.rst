[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk describe-environment-managed-action-history:


*******************************************
describe-environment-managed-action-history
*******************************************



===========
Description
===========



Lists an environment's completed and failed managed actions.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticbeanstalk-2010-12-01/DescribeEnvironmentManagedActionHistory>`_


========
Synopsis
========

::

    describe-environment-managed-action-history
  [--environment-id <value>]
  [--environment-name <value>]
  [--next-token <value>]
  [--max-items <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--environment-id`` (string)


  The environment ID of the target environment.

  

``--environment-name`` (string)


  The name of the target environment.

  

``--next-token`` (string)


  The pagination token returned by a previous request.

  

``--max-items`` (integer)


  The maximum number of items to return for a single request.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ManagedActionHistoryItems -> (list)

  

  A list of completed and failed managed actions.

  

  (structure)

    

    The record of a completed or failed managed action.

    

    ActionId -> (string)

      

      A unique identifier for the managed action.

      

      

    ActionType -> (string)

      

      The type of the managed action.

      

      

    ActionDescription -> (string)

      

      A description of the managed action.

      

      

    FailureType -> (string)

      

      If the action failed, the type of failure.

      

      

    Status -> (string)

      

      The status of the action.

      

      

    FailureDescription -> (string)

      

      If the action failed, a description of the failure.

      

      

    ExecutedTime -> (timestamp)

      

      The date and time that the action started executing.

      

      

    FinishedTime -> (timestamp)

      

      The date and time that the action finished executing.

      

      

    

  

NextToken -> (string)

  

  A pagination token that you pass to  describe-environment-managed-action-history to get the next page of results.

  

  

