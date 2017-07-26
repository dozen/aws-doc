[ :ref:`aws <cli:aws>` . :ref:`codepipeline <cli:aws codepipeline>` ]

.. _cli:aws codepipeline update-pipeline:


***************
update-pipeline
***************



===========
Description
===========



Updates a specified pipeline with edits or changes to its structure. Use a JSON file with the pipeline structure in conjunction with update-pipeline to provide the full structure of the pipeline. Updating the pipeline increases the version number of the pipeline by 1.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codepipeline-2015-07-09/UpdatePipeline>`_


========
Synopsis
========

::

    update-pipeline
  --pipeline <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--pipeline`` (structure)


  The name of the pipeline to be updated.

  



JSON Syntax::

  {
    "name": "string",
    "roleArn": "string",
    "artifactStore": {
      "type": "S3",
      "location": "string",
      "encryptionKey": {
        "id": "string",
        "type": "KMS"
      }
    },
    "stages": [
      {
        "name": "string",
        "blockers": [
          {
            "name": "string",
            "type": "Schedule"
          }
          ...
        ],
        "actions": [
          {
            "name": "string",
            "actionTypeId": {
              "category": "Source"|"Build"|"Deploy"|"Test"|"Invoke"|"Approval",
              "owner": "AWS"|"ThirdParty"|"Custom",
              "provider": "string",
              "version": "string"
            },
            "runOrder": integer,
            "configuration": {"string": "string"
              ...},
            "outputArtifacts": [
              {
                "name": "string"
              }
              ...
            ],
            "inputArtifacts": [
              {
                "name": "string"
              }
              ...
            ],
            "roleArn": "string"
          }
          ...
        ]
      }
      ...
    ],
    "version": integer
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To update the structure of a pipeline**

This example updates the structure of a pipeline by using a pre-defined JSON file (MyFirstPipeline.json) to supply the new structure.

Command::

  aws codepipeline update-pipeline --cli-input-json file://MyFirstPipeline.json
  
Sample JSON file contents::
  
  {
   "pipeline": {
    "roleArn": "arn:aws:iam::111111111111:role/AWS-CodePipeline-Service",
    "stages": [
      {
        "name": "Source",
        "actions": [
          {
            "inputArtifacts": [],
            "name": "Source",
            "actionTypeId": {
              "category": "Source",
              "owner": "AWS",
              "version": "1",
              "provider": "S3"
            },
            "outputArtifacts": [
              {
                "name": "MyApp"
              }
            ],
            "configuration": {
              "S3Bucket": "awscodepipeline-demo-bucket2",
              "S3ObjectKey": "aws-codepipeline-s3-aws-codedeploy_linux.zip"
            },
            "runOrder": 1
          }
        ]
      },
      {
        "name": "Beta",
        "actions": [
          {
            "inputArtifacts": [
              {
                "name": "MyApp"
              }
            ],
            "name": "CodePipelineDemoFleet",
            "actionTypeId": {
              "category": "Deploy",
              "owner": "AWS",
              "version": "1",
              "provider": "CodeDeploy"
            },
            "outputArtifacts": [],
            "configuration": {
              "ApplicationName": "CodePipelineDemoApplication",
              "DeploymentGroupName": "CodePipelineDemoFleet"
            },
            "runOrder": 1
          }
        ]
      }
    ],
    "artifactStore": {
      "type": "S3",
      "location": "codepipeline-us-east-1-11EXAMPLE11"
    },
    "name": "MyFirstPipeline",
    "version": 1
   }
  }


Output::

  {
   "pipeline": {
    "artifactStore": {
      "location": "codepipeline-us-east-1-11EXAMPLE11",
      "type": "S3"
    },
    "name": "MyFirstPipeline",
    "roleArn": "arn:aws:iam::111111111111:role/AWS-CodePipeline-Service",
    "stages": [
      {
        "actions": [
          {
            "actionTypeId": {
              "__type": "ActionTypeId",
              "category": "Source",
              "owner": "AWS",
              "provider": "S3",
              "version": "1"
            },
            "configuration": {
              "S3Bucket": "awscodepipeline-demo-bucket2",
              "S3ObjectKey": "aws-codepipeline-s3-aws-codedeploy_linux.zip"
            },
            "inputArtifacts": [],
            "name": "Source",
            "outputArtifacts": [
              {
                "name": "MyApp"
              }
            ],
            "runOrder": 1
          }
        ],
        "name": "Source"
      },
      {
        "actions": [
          {
            "actionTypeId": {
              "__type": "ActionTypeId",
              "category": "Deploy",
              "owner": "AWS",
              "provider": "CodeDeploy",
              "version": "1"
            },
            "configuration": {
              "ApplicationName": "CodePipelineDemoApplication",
              "DeploymentGroupName": "CodePipelineDemoFleet"
            },
            "inputArtifacts": [
              {
                "name": "MyApp"
              }
            ],
            "name": "CodePipelineDemoFleet",
            "outputArtifacts": [],
            "runOrder": 1
          }
        ],
        "name": "Beta"
      }
    ],
    "version": 3
   }
  }

======
Output
======

pipeline -> (structure)

  

  The structure of the updated pipeline.

  

  name -> (string)

    

    The name of the action to be performed.

    

    

  roleArn -> (string)

    

    The Amazon Resource Name (ARN) for AWS CodePipeline to use to either perform actions with no actionRoleArn, or to use to assume roles for actions with an actionRoleArn.

    

    

  artifactStore -> (structure)

    

    Represents the context of an action within the stage of a pipeline to a job worker. 

    

    type -> (string)

      

      The type of the artifact store, such as S3.

      

      

    location -> (string)

      

      The Amazon S3 bucket used for storing the artifacts for a pipeline. You can specify the name of an S3 bucket but not a folder within the bucket. A folder to contain the pipeline artifacts is created for you based on the name of the pipeline. You can use any Amazon S3 bucket in the same AWS Region as the pipeline to store your pipeline artifacts.

      

      

    encryptionKey -> (structure)

      

      The encryption key used to encrypt the data in the artifact store, such as an AWS Key Management Service (AWS KMS) key. If this is undefined, the default key for Amazon S3 is used.

      

      id -> (string)

        

        The ID used to identify the key. For an AWS KMS key, this is the key ID or key ARN.

        

        

      type -> (string)

        

        The type of encryption key, such as an AWS Key Management Service (AWS KMS) key. When creating or updating a pipeline, the value must be set to 'KMS'.

        

        

      

    

  stages -> (list)

    

    The stage in which to perform the action.

    

    (structure)

      

      Represents information about a stage and its definition.

      

      name -> (string)

        

        The name of the stage.

        

        

      blockers -> (list)

        

        Reserved for future use.

        

        (structure)

          

          Reserved for future use.

          

          name -> (string)

            

            Reserved for future use.

            

            

          type -> (string)

            

            Reserved for future use.

            

            

          

        

      actions -> (list)

        

        The actions included in a stage.

        

        (structure)

          

          Represents information about an action declaration.

          

          name -> (string)

            

            The action declaration's name.

            

            

          actionTypeId -> (structure)

            

            The configuration information for the action type.

            

            category -> (string)

              

              A category defines what kind of action can be taken in the stage, and constrains the provider type for the action. Valid categories are limited to one of the values below.

              

              

            owner -> (string)

              

              The creator of the action being called.

              

              

            provider -> (string)

              

              The provider of the service being called by the action. Valid providers are determined by the action category. For example, an action in the Deploy category type might have a provider of AWS CodeDeploy, which would be specified as CodeDeploy.

              

              

            version -> (string)

              

              A string that identifies the action type.

              

              

            

          runOrder -> (integer)

            

            The order in which actions are run.

            

            

          configuration -> (map)

            

            The action declaration's configuration.

            

            key -> (string)

              

              

            value -> (string)

              

              

            

          outputArtifacts -> (list)

            

            The name or ID of the result of the action declaration, such as a test or build artifact.

            

            (structure)

              

              Represents information about the output of an action.

              

              name -> (string)

                

                The name of the output of an artifact, such as "My App".

                 

                The input artifact of an action must exactly match the output artifact declared in a preceding action, but the input artifact does not have to be the next action in strict sequence from the action that provided the output artifact. Actions in parallel can declare different output artifacts, which are in turn consumed by different following actions.

                 

                Output artifact names must be unique within a pipeline.

                

                

              

            

          inputArtifacts -> (list)

            

            The name or ID of the artifact consumed by the action, such as a test or build artifact.

            

            (structure)

              

              Represents information about an artifact to be worked on, such as a test or build artifact.

              

              name -> (string)

                

                The name of the artifact to be worked on, for example, "My App".

                 

                The input artifact of an action must exactly match the output artifact declared in a preceding action, but the input artifact does not have to be the next action in strict sequence from the action that provided the output artifact. Actions in parallel can declare different output artifacts, which are in turn consumed by different following actions.

                

                

              

            

          roleArn -> (string)

            

            The ARN of the IAM service role that will perform the declared action. This is assumed through the roleArn for the pipeline.

            

            

          

        

      

    

  version -> (integer)

    

    The version number of the pipeline. A new pipeline always has a version number of 1. This number is automatically incremented when a pipeline is updated.

    

    

  

