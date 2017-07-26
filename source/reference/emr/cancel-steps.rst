[ :ref:`aws <cli:aws>` . :ref:`emr <cli:aws emr>` ]

.. _cli:aws emr cancel-steps:


************
cancel-steps
************



===========
Description
===========



Cancels a pending step or steps in a running cluster. Available only in Amazon EMR versions 4.8.0 and later, excluding version 5.0.0. A maximum of 256 steps are allowed in each cancel-steps request. cancel-steps is idempotent but asynchronous; it does not guarantee a step will be canceled, even if the request is successfully submitted. You can only cancel steps that are in a ``PENDING`` state.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticmapreduce-2009-03-31/CancelSteps>`_


========
Synopsis
========

::

    cancel-steps
  [--cluster-id <value>]
  [--step-ids <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cluster-id`` (string)


  The ``ClusterID`` for which specified steps will be canceled. Use  run-job-flow and  list-clusters to get ClusterIDs. 

  

``--step-ids`` (list)


  The list of ``StepIDs`` to cancel. Use  list-steps to get steps and their states for the specified cluster.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

CancelStepsInfoList -> (list)

  

  A list of  CancelStepsInfo , which shows the status of specified cancel requests for each ``StepID`` specified.

  

  (structure)

    

    Specification of the status of a cancel-steps request. Available only in Amazon EMR version 4.8.0 and later, excluding version 5.0.0.

    

    StepId -> (string)

      

      The encrypted StepId of a step.

      

      

    Status -> (string)

      

      The status of a cancel-steps Request. The value may be SUBMITTED or FAILED.

      

      

    Reason -> (string)

      

      The reason for the failure if the cancel-steps request fails.

      

      

    

  

