[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm describe-effective-instance-associations:


****************************************
describe-effective-instance-associations
****************************************



===========
Description
===========



All associations for the instance(s).



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/DescribeEffectiveInstanceAssociations>`_


========
Synopsis
========

::

    describe-effective-instance-associations
  --instance-id <value>
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-id`` (string)


  The instance ID for which you want to view all associations.

  

``--max-results`` (integer)


  The maximum number of items to return for this call. The call also returns a token that you can specify in a subsequent call to get the next set of results.

  

``--next-token`` (string)


  The token for the next set of items to return. (You received this token from a previous call.)

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get details of the effective associations for an instance**

This example describes the effective associations for an instance.

Command::

  aws ssm describe-effective-instance-associations --instance-id "i-0000293ffd8c57862"
  
Output::

  {
    "Associations": [
        {
            "InstanceId": "i-0000293ffd8c57862",
            "Content": "{\n    \"schemaVersion\": \"1.2\",\n    \"description\": \"Update the Amazon SSM Agent to the latest version or specified version.\",\n    \"parameters\": {\n        \"version\": {\n            \"default\": \"\",\n            \"description\": \"(Optional) A specific version of the Amazon SSM Agent to install. If not specified, the agent will be updated to the latest version.\",\n            \"type\": \"String\"\n        },\n        \"allowDowngrade\": {\n            \"default\": \"false\",\n            \"description\": \"(Optional) Allow the Amazon SSM Agent service to be downgraded to an earlier version. If set to false, the service can be upgraded to newer versions only (default). If set to true, specify the earlier version.\",\n            \"type\": \"String\",\n            \"allowedValues\": [\n                \"true\",\n                \"false\"\n            ]\n        }\n    },\n    \"runtimeConfig\": {\n        \"aws:updateSsmAgent\": {\n            \"properties\": [\n                {\n                \"agentName\": \"amazon-ssm-agent\",\n                \"source\": \"https://s3.{Region}.amazonaws.com/amazon-ssm-{Region}/ssm-agent-manifest.json\",\n                \"allowDowngrade\": \"{{ allowDowngrade }}\",\n                \"targetVersion\": \"{{ version }}\"\n                }\n            ]\n        }\n    }\n}\n",
            "AssociationId": "d8617c07-2079-4c18-9847-1655fc2698b0"
        }
    ]
  }


======
Output
======

Associations -> (list)

  

  The associations for the requested instance.

  

  (structure)

    

    One or more association documents on the instance. 

    

    AssociationId -> (string)

      

      The association ID.

      

      

    InstanceId -> (string)

      

      The instance ID.

      

      

    Content -> (string)

      

      The content of the association document for the instance(s).

      

      

    

  

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  

