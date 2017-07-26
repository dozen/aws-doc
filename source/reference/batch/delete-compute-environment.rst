[ :ref:`aws <cli:aws>` . :ref:`batch <cli:aws batch>` ]

.. _cli:aws batch delete-compute-environment:


**************************
delete-compute-environment
**************************



===========
Description
===========



Deletes an AWS Batch compute environment.

 

Before you can delete a compute environment, you must set its state to ``DISABLED`` with the  update-compute-environment API operation and disassociate it from any job queues with the  update-job-queue API operation.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/batch-2016-08-10/DeleteComputeEnvironment>`_


========
Synopsis
========

::

    delete-compute-environment
  --compute-environment <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--compute-environment`` (string)


  The name or Amazon Resource Name (ARN) of the compute environment to delete. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete a compute environment**

This example deletes the `P2OnDemand` compute environment.

Command::

  aws batch delete-compute-environment --compute-environment P2OnDemand


======
Output
======

