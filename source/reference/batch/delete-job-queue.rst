[ :ref:`aws <cli:aws>` . :ref:`batch <cli:aws batch>` ]

.. _cli:aws batch delete-job-queue:


****************
delete-job-queue
****************



===========
Description
===========



Deletes the specified job queue. You must first disable submissions for a queue with the  update-job-queue operation and terminate any jobs that have not completed with the  terminate-job .

 

It is not necessary to disassociate compute environments from a queue before submitting a ``delete-job-queue`` request. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/batch-2016-08-10/DeleteJobQueue>`_


========
Synopsis
========

::

    delete-job-queue
  --job-queue <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--job-queue`` (string)


  The short name or full Amazon Resource Name (ARN) of the queue to delete. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete a job queue**

This example deletes the GPGPU job queue.

Command::

  aws batch delete-job-queue --job-queue GPGPU


======
Output
======

