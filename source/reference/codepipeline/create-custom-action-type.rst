[ :ref:`aws <cli:aws>` . :ref:`codepipeline <cli:aws codepipeline>` ]

.. _cli:aws codepipeline create-custom-action-type:


*************************
create-custom-action-type
*************************



===========
Description
===========



Creates a new custom action that can be used in all pipelines associated with the AWS account. Only used for custom actions.



========
Synopsis
========

::

    create-custom-action-type
  --category <value>
  --provider <value>
  [--settings <value>]
  [--configuration-properties <value>]
  --input-artifact-details <value>
  --output-artifact-details <value>
  --action-version <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--category`` (string)


  The category of the custom action, such as a source action or a build action.

  

  Possible values:

  
  *   ``Source``

  
  *   ``Build``

  
  *   ``Deploy``

  
  *   ``Test``

  
  *   ``Invoke``

  

  

``--provider`` (string)


  The provider of the service used in the custom action, such as AWS CodeDeploy.

  

``--settings`` (structure)


  Returns information about the settings for an action type. 

  



Shorthand Syntax::

    thirdPartyConfigurationUrl=string,entityUrlTemplate=string,executionUrlTemplate=string,revisionUrlTemplate=string




JSON Syntax::

  {
    "thirdPartyConfigurationUrl": "string",
    "entityUrlTemplate": "string",
    "executionUrlTemplate": "string",
    "revisionUrlTemplate": "string"
  }



``--configuration-properties`` (list)


  The configuration properties for the custom action.

  



Shorthand Syntax::

    name=string,required=boolean,key=boolean,secret=boolean,queryable=boolean,description=string,type=string ...




JSON Syntax::

  [
    {
      "name": "string",
      "required": true|false,
      "key": true|false,
      "secret": true|false,
      "queryable": true|false,
      "description": "string",
      "type": "String"|"Number"|"Boolean"
    }
    ...
  ]



``--input-artifact-details`` (structure)


  Returns information about the details of an artifact.

  



Shorthand Syntax::

    minimumCount=integer,maximumCount=integer




JSON Syntax::

  {
    "minimumCount": integer,
    "maximumCount": integer
  }



``--output-artifact-details`` (structure)


  Returns information about the details of an artifact.

  



Shorthand Syntax::

    minimumCount=integer,maximumCount=integer




JSON Syntax::

  {
    "minimumCount": integer,
    "maximumCount": integer
  }



``--action-version`` (string)


  The version number of the custom action. 

   

  .. note::

    A newly-created custom action is always assigned a version number of ``1`` . This is required.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To create a custom action**

This example creates a custom action for AWS CodePipeline using an already-created JSON file (here named MyCustomAction.json) that contains the structure of the custom action. For more information about the requirements for creating a custom action, including the structure of the file, see the AWS CodePipeline User Guide.

Command::

  aws codepipeline create-custom-action-type --cli-input-json file://MyCustomAction.json
  
JSON file sample contents::
  
  {
   "actionType": {
    "actionConfigurationProperties": [
      {
        "description": "The name of the build project must be provided when this action is added to the pipeline.",
        "key": true,
        "name": "MyJenkinsExampleBuildProject",
        "queryable": false,
        "required": true,
        "secret": false
      }
    ],
    "id": {
      "__type": "ActionTypeId",
      "category": "Build",
      "owner": "Custom",
      "provider": "MyJenkinsProviderName",
      "version": "1"
    },
    "inputArtifactDetails": {
      "maximumCount": 1,
      "minimumCount": 0
    },
    "outputArtifactDetails": {
      "maximumCount": 1,
      "minimumCount": 0
    },
    "settings": {
      "entityUrlTemplate": "https://192.0.2.4/job/{Config:ProjectName}/",
      "executionUrlTemplate": "https://192.0.2.4/job/{Config:ProjectName}/lastSuccessfulBuild/{ExternalExecutionId}/"
    }
   }
  }

Output::

  This command returns the structure of the custom action.

======
Output
======

actionType -> (structure)

  

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

      

      

    

  

