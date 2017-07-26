[ :ref:`aws <cli:aws>` . :ref:`codepipeline <cli:aws codepipeline>` ]

.. _cli:aws codepipeline delete-pipeline:


***************
delete-pipeline
***************



===========
Description
===========



Deletes the specified pipeline.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codepipeline-2015-07-09/DeletePipeline>`_


========
Synopsis
========

::

    delete-pipeline
  --name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the pipeline to be deleted.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete a pipeline**

This example deletes a pipeline named MySecondPipeline from AWS CodePipeline. Use the list-pipelines command to view a list of pipelines associated with your AWS account.

Command::

  aws codepipeline delete-pipeline --name MySecondPipeline


Output::

  None.

======
Output
======

None