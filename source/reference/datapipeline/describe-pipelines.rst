[ :ref:`aws <cli:aws>` . :ref:`datapipeline <cli:aws datapipeline>` ]

.. _cli:aws datapipeline describe-pipelines:


******************
describe-pipelines
******************



===========
Description
===========



Retrieves metadata about one or more pipelines. The information retrieved includes the name of the pipeline, the pipeline identifier, its current state, and the user account that owns the pipeline. Using account credentials, you can retrieve metadata about pipelines that you or your IAM users have created. If you are using an IAM user account, you can retrieve metadata about only those pipelines for which you have read permissions.

 

To retrieve the full pipeline definition instead of metadata about the pipeline, call  get-pipeline-definition .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/datapipeline-2012-10-29/DescribePipelines>`_


========
Synopsis
========

::

    describe-pipelines
  --pipeline-ids <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--pipeline-ids`` (list)


  The IDs of the pipelines to describe. You can pass as many as 25 identifiers in a single call. To obtain pipeline IDs, call  list-pipelines .

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe your pipelines**

This example describes the specified pipeline::

   aws datapipeline describe-pipelines --pipeline-ids df-00627471SOVYZEXAMPLE
   
The following is example output::

  {
    "pipelineDescriptionList": [
        {
            "fields": [
                {
                    "stringValue": "PENDING",
                    "key": "@pipelineState"
                },
                {
                    "stringValue": "my-pipeline",
                    "key": "name"
                },
                {
                    "stringValue": "2015-04-07T16:05:58",
                    "key": "@creationTime"
                },
                {
                    "stringValue": "df-00627471SOVYZEXAMPLE",
                    "key": "@id"
                },
                {
                    "stringValue": "123456789012",
                    "key": "pipelineCreator"
                },
                {
                    "stringValue": "PIPELINE",
                    "key": "@sphere"
                },
                {
                    "stringValue": "123456789012",
                    "key": "@userId"
                },
                {
                    "stringValue": "123456789012",
                    "key": "@accountId"
                },
                {
                    "stringValue": "my-pipeline-token",
                    "key": "uniqueId"
                }
            ],
            "pipelineId": "df-00627471SOVYZEXAMPLE",
            "name": "my-pipeline",
            "tags": []
        }
    ]
  }


======
Output
======

pipelineDescriptionList -> (list)

  

  An array of descriptions for the specified pipelines.

  

  (structure)

    

    Contains pipeline metadata.

    

    pipelineId -> (string)

      

      The pipeline identifier that was assigned by AWS Data Pipeline. This is a string of the form ``df-297EG78HU43EEXAMPLE`` .

      

      

    name -> (string)

      

      The name of the pipeline.

      

      

    fields -> (list)

      

      A list of read-only fields that contain metadata about the pipeline: @userId, @accountId, and @pipelineState.

      

      (structure)

        

        A key-value pair that describes a property of a pipeline object. The value is specified as either a string value (``StringValue`` ) or a reference to another object (``RefValue`` ) but not as both.

        

        key -> (string)

          

          The field identifier.

          

          

        stringValue -> (string)

          

          The field value, expressed as a String.

          

          

        refValue -> (string)

          

          The field value, expressed as the identifier of another object.

          

          

        

      

    description -> (string)

      

      Description of the pipeline.

      

      

    tags -> (list)

      

      A list of tags to associated with a pipeline. Tags let you control access to pipelines. For more information, see `Controlling User Access to Pipelines <http://docs.aws.amazon.com/datapipeline/latest/DeveloperGuide/dp-control-access.html>`_ in the *AWS Data Pipeline Developer Guide* .

      

      (structure)

        

        Tags are key/value pairs defined by a user and associated with a pipeline to control access. AWS Data Pipeline allows you to associate ten tags per pipeline. For more information, see `Controlling User Access to Pipelines <http://docs.aws.amazon.com/datapipeline/latest/DeveloperGuide/dp-control-access.html>`_ in the *AWS Data Pipeline Developer Guide* .

        

        key -> (string)

          

          The key name of a tag defined by a user. For more information, see `Controlling User Access to Pipelines <http://docs.aws.amazon.com/datapipeline/latest/DeveloperGuide/dp-control-access.html>`_ in the *AWS Data Pipeline Developer Guide* .

          

          

        value -> (string)

          

          The optional value portion of a tag defined by a user. For more information, see `Controlling User Access to Pipelines <http://docs.aws.amazon.com/datapipeline/latest/DeveloperGuide/dp-control-access.html>`_ in the *AWS Data Pipeline Developer Guide* .

          

          

        

      

    

  

