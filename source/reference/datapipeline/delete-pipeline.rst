[ :ref:`aws <cli:aws>` . :ref:`datapipeline <cli:aws datapipeline>` ]

.. _cli:aws datapipeline delete-pipeline:


***************
delete-pipeline
***************



===========
Description
===========



Deletes a pipeline, its pipeline definition, and its run history. AWS Data Pipeline attempts to cancel instances associated with the pipeline that are currently being processed by task runners.

 

Deleting a pipeline cannot be undone. You cannot query or restore a deleted pipeline. To temporarily pause a pipeline instead of deleting it, call  set-status with the status set to ``PAUSE`` on individual components. Components that are paused by  set-status can be resumed.



========
Synopsis
========

::

    delete-pipeline
  --pipeline-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--pipeline-id`` (string)


  The ID of the pipeline.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete a pipeline**

This example deletes the specified pipeline::

   aws datapipeline delete-pipeline --pipeline-id df-00627471SOVYZEXAMPLE


======
Output
======

None