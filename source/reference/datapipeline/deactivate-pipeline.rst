[ :ref:`aws <cli:aws>` . :ref:`datapipeline <cli:aws datapipeline>` ]

.. _cli:aws datapipeline deactivate-pipeline:


*******************
deactivate-pipeline
*******************



===========
Description
===========



Deactivates the specified running pipeline. The pipeline is set to the ``DEACTIVATING`` state until the deactivation process completes.

 

To resume a deactivated pipeline, use  activate-pipeline . By default, the pipeline resumes from the last completed execution. Optionally, you can specify the date and time to resume the pipeline.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/datapipeline-2012-10-29/DeactivatePipeline>`_


========
Synopsis
========

::

    deactivate-pipeline
  --pipeline-id <value>
  [--cancel-active | --no-cancel-active]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--pipeline-id`` (string)


  The ID of the pipeline.

  

``--cancel-active`` | ``--no-cancel-active`` (boolean)


  Indicates whether to cancel any running objects. The default is true, which sets the state of any running objects to ``CANCELED`` . If this value is false, the pipeline is deactivated after all running objects finish.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To deactivate a pipeline**

This example deactivates the specified pipeline::

   aws datapipeline deactivate-pipeline --pipeline-id df-00627471SOVYZEXAMPLE
   
To deactivate the pipeline only after all running activities finish, use the following command::

   aws datapipeline deactivate-pipeline --pipeline-id df-00627471SOVYZEXAMPLE --no-cancel-active


======
Output
======

