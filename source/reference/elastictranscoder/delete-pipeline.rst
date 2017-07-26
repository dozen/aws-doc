[ :ref:`aws <cli:aws>` . :ref:`elastictranscoder <cli:aws elastictranscoder>` ]

.. _cli:aws elastictranscoder delete-pipeline:


***************
delete-pipeline
***************



===========
Description
===========



The delete-pipeline operation removes a pipeline.

 

You can only delete a pipeline that has never been used or that is not currently in use (doesn't contain any active jobs). If the pipeline is currently in use, ``delete-pipeline`` returns an error. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elastictranscoder-2012-09-25/DeletePipeline>`_


========
Synopsis
========

::

    delete-pipeline
  --id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--id`` (string)


  The identifier of the pipeline that you want to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

