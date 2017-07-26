[ :ref:`aws <cli:aws>` . :ref:`codepipeline <cli:aws codepipeline>` ]

.. _cli:aws codepipeline list-pipelines:


**************
list-pipelines
**************



===========
Description
===========



Gets a summary of all of the pipelines associated with your account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codepipeline-2015-07-09/ListPipelines>`_


========
Synopsis
========

::

    list-pipelines
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--next-token`` (string)


  An identifier that was returned from the previous list pipelines call, which can be used to return the next set of pipelines in the list.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To view a list of pipelines**

This example lists all AWS CodePipeline pipelines associated with the user's AWS account.

Command::

  aws codepipeline list-pipelines

Output::

  {
    "pipelines": [
        {
            "updated": 1439504274.641,
            "version": 1,
            "name": "MyFirstPipeline",
            "created": 1439504274.641
        },
        {
            "updated": 1436461837.992,
            "version": 2,
            "name": "MySecondPipeline",
            "created": 1436460801.381
        }
	]	
  }

======
Output
======

pipelines -> (list)

  

  The list of pipelines.

  

  (structure)

    

    Returns a summary of a pipeline.

    

    name -> (string)

      

      The name of the pipeline.

      

      

    version -> (integer)

      

      The version number of the pipeline.

      

      

    created -> (timestamp)

      

      The date and time the pipeline was created, in timestamp format.

      

      

    updated -> (timestamp)

      

      The date and time of the last update to the pipeline, in timestamp format.

      

      

    

  

nextToken -> (string)

  

  If the amount of returned information is significantly large, an identifier is also returned which can be used in a subsequent list pipelines call to return the next set of pipelines in the list.

  

  

