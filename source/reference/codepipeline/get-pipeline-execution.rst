[ :ref:`aws <cli:aws>` . :ref:`codepipeline <cli:aws codepipeline>` ]

.. _cli:aws codepipeline get-pipeline-execution:


**********************
get-pipeline-execution
**********************



===========
Description
===========



Returns information about an execution of a pipeline, including details about artifacts, the pipeline execution ID, and the name, version, and status of the pipeline.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codepipeline-2015-07-09/GetPipelineExecution>`_


========
Synopsis
========

::

    get-pipeline-execution
  --pipeline-name <value>
  --pipeline-execution-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--pipeline-name`` (string)


  The name of the pipeline about which you want to get execution details.

  

``--pipeline-execution-id`` (string)


  The ID of the pipeline execution about which you want to get execution details.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

pipelineExecution -> (structure)

  

  Represents information about the execution of a pipeline.

  

  pipelineName -> (string)

    

    The name of the pipeline that was executed.

    

    

  pipelineVersion -> (integer)

    

    The version number of the pipeline that was executed.

    

    

  pipelineExecutionId -> (string)

    

    The ID of the pipeline execution.

    

    

  status -> (string)

    

    The status of the pipeline execution.

     

     
    * InProgress: The pipeline execution is currently running. 
     
    * Succeeded: The pipeline execution completed successfully.  
     
    * Superseded: While this pipeline execution was waiting for the next stage to be completed, a newer pipeline execution caught up and continued through the pipeline instead.  
     
    * Failed: The pipeline execution did not complete successfully. 
     

    

    

  artifactRevisions -> (list)

    

    A list of ArtifactRevision objects included in a pipeline execution.

    

    (structure)

      

      Represents revision details of an artifact. 

      

      name -> (string)

        

        The name of an artifact. This name might be system-generated, such as "MyApp", or might be defined by the user when an action is created.

        

        

      revisionId -> (string)

        

        The revision ID of the artifact.

        

        

      revisionChangeIdentifier -> (string)

        

        An additional identifier for a revision, such as a commit date or, for artifacts stored in Amazon S3 buckets, the ETag value.

        

        

      revisionSummary -> (string)

        

        Summary information about the most recent revision of the artifact. For GitHub and AWS CodeCommit repositories, the commit message. For Amazon S3 buckets or actions, the user-provided content of a ``codepipeline-artifact-revision-summary`` key specified in the object metadata.

        

        

      created -> (timestamp)

        

        The date and time when the most recent revision of the artifact was created, in timestamp format.

        

        

      revisionUrl -> (string)

        

        The commit ID for the artifact revision. For artifacts stored in GitHub or AWS CodeCommit repositories, the commit ID is linked to a commit details page.

        

        

      

    

  

