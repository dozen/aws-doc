[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector preview-agents-for-resource-group:


*********************************
preview-agents-for-resource-group
*********************************



===========
Description
===========



Previews the agents installed on the EC2 instances that are included in the application created with the specified resource group.



========
Synopsis
========

::

    preview-agents-for-resource-group
  --resource-group-arn <value>
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--resource-group-arn`` (string)


  The ARN of the resource group that is used to create an application.

  

``--next-token`` (string)


  You can use this parameter when paginating results. Set the value of this parameter to 'null' on your first call to the **preview-agents-for-resource-group** action. Subsequent calls to the action fill **nextToken** in the request with the value of **NextToken** from previous response to continue listing data.

  

``--max-results`` (integer)


  You can use this parameter to indicate the maximum number of items you want in the response. The default value is 10. The maximum value is 500.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

agentPreviewList -> (list)

  

  The resulting list of agents.

  

  (structure)

    

    This data type is used as a response element in the  preview-agents-for-resource-group action.

    

    agentId -> (string)

      

      The id of the EC2 instance where the agent is intalled.

      

      

    autoScalingGroup -> (string)

      

      The autoscaling group for the EC2 instance where the agent is installed.

      

      

    

  

nextToken -> (string)

  

  When a response is generated, if there is more data to be listed, this parameter is present in the response and contains the value to use for the **nextToken** parameter in a subsequent pagination request. If there is no more data to be listed, this parameter is set to 'null'.

  

  

