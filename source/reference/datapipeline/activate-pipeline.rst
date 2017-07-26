[ :ref:`aws <cli:aws>` . :ref:`datapipeline <cli:aws datapipeline>` ]

.. _cli:aws datapipeline activate-pipeline:


*****************
activate-pipeline
*****************



===========
Description
===========



Validates the specified pipeline and starts processing pipeline tasks. If the pipeline does not pass validation, activation fails.

 

If you need to pause the pipeline to investigate an issue with a component, such as a data source or script, call  deactivate-pipeline .

 

To activate a finished pipeline, modify the end date for the pipeline and then activate it.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/datapipeline-2012-10-29/ActivatePipeline>`_


========
Synopsis
========

::

    activate-pipeline
  --pipeline-id <value>
  [--parameter-values <value>]
  [--start-timestamp <value>]
  [--parameter-values-uri <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--pipeline-id`` (string)


  The ID of the pipeline.

  

``--parameter-values`` (string)
The JSON parameter values. You can specify these as key-value pairs in the key=value format. Multiple parameters are separated by a space. For list type parameter values you can use the same key name and specify each value as a key value pair. e.g. arrayValue=value1 arrayValue=value2 

``--start-timestamp`` (timestamp)


  The date and time to resume the pipeline. By default, the pipeline resumes from the last completed execution.

  

``--parameter-values-uri`` (string)
The JSON parameter values. If the parameter values are in a file you can use the file://syntax to specify a filename. You can optionally provide these in pipeline definition as well. Parameter values provided on command line would replace the one in definition. 

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To activate a pipeline**

This example activates the specified pipeline::

   aws datapipeline activate-pipeline --pipeline-id df-00627471SOVYZEXAMPLE

To activate the pipeline at a specific date and time, use the following command::

   aws datapipeline activate-pipeline --pipeline-id df-00627471SOVYZEXAMPLE --start-timestamp 2015-04-07T00:00:00Z


======
Output
======

