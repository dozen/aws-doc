[ :ref:`aws <cli:aws>` . :ref:`codepipeline <cli:aws codepipeline>` ]

.. _cli:aws codepipeline list-action-types:


*****************
list-action-types
*****************



===========
Description
===========



Gets a summary of all AWS CodePipeline action types associated with your account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codepipeline-2015-07-09/ListActionTypes>`_


========
Synopsis
========

::

    list-action-types
  [--action-owner-filter <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--action-owner-filter`` (string)


  Filters the list of action types to those created by a specified entity.

  

  Possible values:

  
  *   ``AWS``

  
  *   ``ThirdParty``

  
  *   ``Custom``

  

  

``--next-token`` (string)


  An identifier that was returned from the previous list action types call, which can be used to return the next set of action types in the list.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To view the action types available**

Used by itself, the list-action-types command returns the structure of all actions available to your AWS account. This example uses the --action-owner-filter option to return only custom actions.

Command::

  aws codepipeline list-action-types --action-owner-filter Custom


Output::

  {
    "actionTypes": [
        {
            "inputArtifactDetails": {
                "maximumCount": 5, 
                "minimumCount": 0
            }, 
            "actionConfigurationProperties": [
                {
                    "secret": false, 
                    "required": true, 
                    "name": "MyJenkinsExampleBuildProject", 
                    "key": true, 
                    "queryable": true
                }
            ], 
            "outputArtifactDetails": {
                "maximumCount": 5, 
                "minimumCount": 0
            }, 
            "id": {
                "category": "Build", 
                "owner": "Custom", 
                "version": "1", 
                "provider": "MyJenkinsProviderName"
            }, 
            "settings": {
                "entityUrlTemplate": "http://192.0.2.4/job/{Config:ProjectName}", 
                "executionUrlTemplate": "http://192.0.2.4/job/{Config:ProjectName}/{ExternalExecutionId}"
            }
        }, 
        {
            "inputArtifactDetails": {
                "maximumCount": 5, 
                "minimumCount": 0
            }, 
            "actionConfigurationProperties": [
                {
                    "secret": false, 
                    "required": true, 
                    "name": "MyJenkinsExampleTestProject", 
                    "key": true, 
                    "queryable": true
                }
            ], 
            "outputArtifactDetails": {
                "maximumCount": 5, 
                "minimumCount": 0
            }, 
            "id": {
                "category": "Test", 
                "owner": "Custom", 
                "version": "1", 
                "provider": "MyJenkinsProviderName"
            }, 
            "settings": {
                "entityUrlTemplate": "http://192.0.2.4/job/{Config:ProjectName}", 
                "executionUrlTemplate": "http://192.0.2.4/job/{Config:ProjectName}/{ExternalExecutionId}"
            }
        }
    ]
  }

======
Output
======

actionTypes -> (list)

  

  Provides details of the action types.

  

  (structure)

    

    Returns information about the details of an action type.

    

    id -> (structure)

      

      Represents information about an action type.

      

      category -> (string)

        

        A category defines what kind of action can be taken in the stage, and constrains the provider type for the action. Valid categories are limited to one of the values below.

        

        

      owner -> (string)

        

        The creator of the action being called.

        

        

      provider -> (string)

        

        The provider of the service being called by the action. Valid providers are determined by the action category. For example, an action in the Deploy category type might have a provider of AWS CodeDeploy, which would be specified as CodeDeploy.

        

        

      version -> (string)

        

        A string that identifies the action type.

        

        

      

    settings -> (structure)

      

      The settings for the action type.

      

      thirdPartyConfigurationUrl -> (string)

        

        The URL of a sign-up page where users can sign up for an external service and perform initial configuration of the action provided by that service.

        

        

      entityUrlTemplate -> (string)

        

        The URL returned to the AWS CodePipeline console that provides a deep link to the resources of the external system, such as the configuration page for an AWS CodeDeploy deployment group. This link is provided as part of the action display within the pipeline.

        

        

      executionUrlTemplate -> (string)

        

        The URL returned to the AWS CodePipeline console that contains a link to the top-level landing page for the external system, such as console page for AWS CodeDeploy. This link is shown on the pipeline view page in the AWS CodePipeline console and provides a link to the execution entity of the external action.

        

        

      revisionUrlTemplate -> (string)

        

        The URL returned to the AWS CodePipeline console that contains a link to the page where customers can update or change the configuration of the external action.

        

        

      

    actionConfigurationProperties -> (list)

      

      The configuration properties for the action type.

      

      (structure)

        

        Represents information about an action configuration property.

        

        name -> (string)

          

          The name of the action configuration property.

          

          

        required -> (boolean)

          

          Whether the configuration property is a required value.

          

          

        key -> (boolean)

          

          Whether the configuration property is a key.

          

          

        secret -> (boolean)

          

          Whether the configuration property is secret. Secrets are hidden from all calls except for GetJobDetails, GetThirdPartyJobDetails, PollForJobs, and PollForThirdPartyJobs.

           

          When updating a pipeline, passing * * * * * without changing any other values of the action will preserve the prior value of the secret.

          

          

        queryable -> (boolean)

          

          Indicates that the proprety will be used in conjunction with PollForJobs. When creating a custom action, an action can have up to one queryable property. If it has one, that property must be both required and not secret.

           

          If you create a pipeline with a custom action type, and that custom action contains a queryable property, the value for that configuration property is subject to additional restrictions. The value must be less than or equal to twenty (20) characters. The value can contain only alphanumeric characters, underscores, and hyphens.

          

          

        description -> (string)

          

          The description of the action configuration property that will be displayed to users.

          

          

        type -> (string)

          

          The type of the configuration property.

          

          

        

      

    inputArtifactDetails -> (structure)

      

      The details of the input artifact for the action, such as its commit ID.

      

      minimumCount -> (integer)

        

        The minimum number of artifacts allowed for the action type.

        

        

      maximumCount -> (integer)

        

        The maximum number of artifacts allowed for the action type.

        

        

      

    outputArtifactDetails -> (structure)

      

      The details of the output artifact of the action, such as its commit ID.

      

      minimumCount -> (integer)

        

        The minimum number of artifacts allowed for the action type.

        

        

      maximumCount -> (integer)

        

        The maximum number of artifacts allowed for the action type.

        

        

      

    

  

nextToken -> (string)

  

  If the amount of returned information is significantly large, an identifier is also returned which can be used in a subsequent list action types call to return the next set of action types in the list.

  

  

