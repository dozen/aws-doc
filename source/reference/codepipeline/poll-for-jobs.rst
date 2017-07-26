[ :ref:`aws <cli:aws>` . :ref:`codepipeline <cli:aws codepipeline>` ]

.. _cli:aws codepipeline poll-for-jobs:


*************
poll-for-jobs
*************



===========
Description
===========



Returns information about any jobs for AWS CodePipeline to act upon.

 

.. warning::

  

  When this API is called, AWS CodePipeline returns temporary credentials for the Amazon S3 bucket used to store artifacts for the pipeline, if the action requires access to that Amazon S3 bucket for input or output artifacts. Additionally, this API returns any secret values defined for the action.

  



========
Synopsis
========

::

    poll-for-jobs
  --action-type-id <value>
  [--max-batch-size <value>]
  [--query-param <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--action-type-id`` (structure)


  Represents information about an action type.

  



Shorthand Syntax::

    category=string,owner=string,provider=string,version=string




JSON Syntax::

  {
    "category": "Source"|"Build"|"Deploy"|"Test"|"Invoke",
    "owner": "AWS"|"ThirdParty"|"Custom",
    "provider": "string",
    "version": "string"
  }



``--max-batch-size`` (integer)


  The maximum number of jobs to return in a poll for jobs call.

  

``--query-param`` (map)


  A map of property names and values. For an action type with no queryable properties, this value must be null or an empty map. For an action type with a queryable property, you must supply that property as a key in the map. Only jobs whose action configuration matches the mapped value will be returned.

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To view any available jobs**

This example returns information about any jobs for a job worker to act upon. This example uses a pre-defined JSON file (MyActionTypeInfo.json) to supply information about the action type for which the job worker processes jobs. This command is only used for custom actions. When this command is called, AWS CodePipeline returns temporary credentials for the Amazon S3 bucket used to store artifacts for the pipeline. This command will also return any secret values defined for the action, if any are defined.

Command::

  aws codepipeline poll-for-jobs --cli-input-json file://MyActionTypeInfo.json

JSON file sample contents::
  
  {
    "actionTypeId": {
      "category": "Test",
      "owner": "Custom",
      "provider": "MyJenkinsProviderName",
      "version": "1"
    }, 
    "maxBatchSize": 5, 
    "queryParam": {
        "ProjectName": "MyJenkinsTestProject"
    }
  }

Output::

  {
   "jobs": [
    {
      "accountId": "111111111111",
      "data": {
        "actionConfiguration": {
          "__type": "ActionConfiguration",
          "configuration": {
            "ProjectName": "MyJenkinsExampleTestProject"
          }
        },
        "actionTypeId": {
          "__type": "ActionTypeId",
          "category": "Test",
          "owner": "Custom",
          "provider": "MyJenkinsProviderName",
          "version": "1"
        },
        "artifactCredentials": {
          "__type": "AWSSessionCredentials",
          "accessKeyId": "AKIAIOSFODNN7EXAMPLE",
          "secretAccessKey": "wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY",
          "sessionToken": "fICCQD6m7oRw0uXOjANBgkqhkiG9w0BAQUFADCBiDELMAkGA1UEBhMCVVMxCzAJBgNVBAgTAldBMRAwDgYDVQQHEwdTZWF0dGxlMQ8wDQYDVQQKEwZBbWF6b24xFDASBgNVBAsTC0lBTSBDb25zb2xlMRIwEAYDVQQDEwlUZXN0Q2lsYWMxHzAdBgkqhkiG9w0BCQEWEG5vb25lQGFtYXpvbi5jb20wHhcNMTEwNDI1MjA0NTIxWhcNMTIwNDI0MjA0NTIxWjCBiDELMAkGA1UEBhMCVVMxCzAJBgNVBAgTAldBMRAwDgYDVQQHEwdTZWF0dGxlMQ8wDQYDVQQKEwZBbWF6b24xFDASBgNVBAsTC0lBTSBDb25zb2xlMRIwEAYDVQQDEwlUZXN0Q2lsYWMxHzAdBgkqhkiG9w0BCQEWEG5vb25lQGFtYXpvbi5jb20wgZ8wDQYJKoZIhvcNAQEBBQADgY0AMIGJAoGBAMaK0dn+a4GmWIWJ21uUSfwfEvySWtC2XADZ4nB+BLYgVIk60CpiwsZ3G93vUEIO3IyNoH/f0wYK8m9TrDHudUZg3qX4waLG5M43q7Wgc/MbQITxOUSQv7c7ugFFDzQGBzZswY6786m86gpEIbb3OhjZnzcvQAaRHhdlQWIMm2nrAgMBAAEwDQYJKoZIhvcNAQEFBQADgYEAtCu4nUhVVxYUntneD9+h8Mg9q6q+auNKyExzyLwaxlAoo7TJHidbtS4J5iNmZgXL0FkbFFBjvSfpJIlJ00zbhNYS5f6GuoEDmFJl0ZxBHjJnyp378OD8uTs7fLvjx79LjSTbNYiytVbZPQUQ5Yaxu2jXnimvw3rrszlaEXAMPLE="
        },
        "inputArtifacts": [
          {
            "__type": "Artifact",
            "location": {
              "s3Location": {
                "bucketName": "codepipeline-us-east-1-11EXAMPLE11",
                "objectKey": "MySecondPipeline/MyAppBuild/EXAMPLE"
              },
              "type": "S3"
            },
            "name": "MyAppBuild"
          }
        ],
        "outputArtifacts": [],
        "pipelineContext": {
          "__type": "PipelineContext",
          "action": {
            "name": "MyJenkinsTest-Action"
          },
          "pipelineName": "MySecondPipeline",
          "stage": {
            "name": "Testing"
          }
        }
      },
      "id": "ef66c259-64f9-EXAMPLE",
      "nonce": "3"
    }
   ]
  }

======
Output
======

jobs -> (list)

  

  Information about the jobs to take action on.

  

  (structure)

    

    Represents information about a job.

    

    id -> (string)

      

      The unique system-generated ID of the job.

      

      

    data -> (structure)

      

      Additional data about a job.

      

      actionTypeId -> (structure)

        

        Represents information about an action type.

        

        category -> (string)

          

          A category defines what kind of action can be taken in the stage, and constrains the provider type for the action. Valid categories are limited to one of the values below. 

          

          

        owner -> (string)

          

          The creator of the action being called. 

          

          

        provider -> (string)

          

          The provider of the service being called by the action. Valid providers are determined by the action category. For example, an action in the Deploy category type might have a provider of AWS CodeDeploy, which would be specified as CodeDeploy.

          

          

        version -> (string)

          

          A string that identifies the action type. 

          

          

        

      actionConfiguration -> (structure)

        

        Represents information about an action configuration.

        

        configuration -> (map)

          

          The configuration data for the action.

          

          key -> (string)

            

            

          value -> (string)

            

            

          

        

      pipelineContext -> (structure)

        

        Represents information about a pipeline to a job worker.

        

        pipelineName -> (string)

          

          The name of the pipeline. This is a user-specified value. Pipeline names must be unique across all pipeline names under an Amazon Web Services account.

          

          

        stage -> (structure)

          

          The stage of the pipeline.

          

          name -> (string)

            

            The name of the stage.

            

            

          

        action -> (structure)

          

          Represents the context of an action within the stage of a pipeline to a job worker.

          

          name -> (string)

            

            The name of the action within the context of a job.

            

            

          

        

      inputArtifacts -> (list)

        

        The artifact supplied to the job.

        

        (structure)

          

          Represents information about an artifact that will be worked upon by actions in the pipeline.

          

          name -> (string)

            

            The artifact's name.

            

            

          revision -> (string)

            

            The artifact's revision ID. Depending on the type of object, this could be a commit ID (GitHub) or a revision ID (Amazon S3).

            

            

          location -> (structure)

            

            The location of an artifact.

            

            type -> (string)

              

              The type of artifact in the location.

              

              

            s3Location -> (structure)

              

              The Amazon S3 bucket that contains the artifact.

              

              bucketName -> (string)

                

                The name of the Amazon S3 bucket. 

                

                

              objectKey -> (string)

                

                The key of the object in the Amazon S3 bucket, which uniquely identifies the object in the bucket. 

                

                

              

            

          

        

      outputArtifacts -> (list)

        

        The output of the job.

        

        (structure)

          

          Represents information about an artifact that will be worked upon by actions in the pipeline.

          

          name -> (string)

            

            The artifact's name.

            

            

          revision -> (string)

            

            The artifact's revision ID. Depending on the type of object, this could be a commit ID (GitHub) or a revision ID (Amazon S3).

            

            

          location -> (structure)

            

            The location of an artifact.

            

            type -> (string)

              

              The type of artifact in the location.

              

              

            s3Location -> (structure)

              

              The Amazon S3 bucket that contains the artifact.

              

              bucketName -> (string)

                

                The name of the Amazon S3 bucket. 

                

                

              objectKey -> (string)

                

                The key of the object in the Amazon S3 bucket, which uniquely identifies the object in the bucket. 

                

                

              

            

          

        

      artifactCredentials -> (structure)

        

        Represents an AWS session credentials object. These credentials are temporary credentials that are issued by AWS Secure Token Service (STS). They can be used to access input and output artifacts in the Amazon S3 bucket used to store artifact for the pipeline in AWS CodePipeline.

        

        accessKeyId -> (string)

          

          The access key for the session.

          

          

        secretAccessKey -> (string)

          

          The secret access key for the session.

          

          

        sessionToken -> (string)

          

          The token for the session.

          

          

        

      continuationToken -> (string)

        

        A system-generated token, such as a AWS CodeDeploy deployment ID, that a job requires in order to continue the job asynchronously.

        

        

      encryptionKey -> (structure)

        

        Represents information about the AWS Key Management Service (AWS KMS) key used to encrypt data in the artifact store.

        

        id -> (string)

          

          The ID of the AWS KMS key.

          

          

        type -> (string)

          

          The type of AWS KMS key, such as a customer master key.

          

          

        

      

    nonce -> (string)

      

      A system-generated random number that AWS CodePipeline uses to ensure that the job is being worked on by only one job worker. This number must be returned in the response.

      

      

    accountId -> (string)

      

      The ID of the AWS account to use when performing the job.

      

      

    

  

