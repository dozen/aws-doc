[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector preview-agents:


**************
preview-agents
**************



===========
Description
===========



Previews the agents installed on the EC2 instances that are part of the specified assessment target.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/inspector-2016-02-16/PreviewAgents>`_


========
Synopsis
========

::

    preview-agents
  --preview-agents-arn <value>
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--preview-agents-arn`` (string)


  The ARN of the assessment target whose agents you want to preview.

  

``--next-token`` (string)


  You can use this parameter when paginating results. Set the value of this parameter to null on your first call to the **preview-agents** action. Subsequent calls to the action fill **nextToken** in the request with the value of **NextToken** from the previous response to continue listing data.

  

``--max-results`` (integer)


  You can use this parameter to indicate the maximum number of items you want in the response. The default value is 10. The maximum value is 500.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To preview agents**

The following ``preview-agents`` command previews the agents installed on the EC2 instances that are part of the assessment target with the ARN of ``arn:aws:inspector:us-west-2:123456789012:target/0-0kFIPusq``::

  aws inspector preview-agents --preview-agents-arn arn:aws:inspector:us-west-2:123456789012:target/0-0kFIPusq

Output::

  {
	"agentPreviews": [
	  {
		"agentId": "i-49113b93"
	  }
	]
  }

For more information, see `Amazon Inspector Assessment Targets`_ in the *Amazon Inspector* guide.

.. _`Amazon Inspector Assessment Targets`: https://docs.aws.amazon.com/inspector/latest/userguide/inspector_applications.html



======
Output
======

agentPreviews -> (list)

  

  The resulting list of agents.

  

  (structure)

    

    Used as a response element in the  preview-agents action.

    

    agentId -> (string)

      

      The ID of the EC2 instance where the agent is installed.

      

      

    autoScalingGroup -> (string)

      

      The Auto Scaling group for the EC2 instance where the agent is installed.

      

      

    

  

nextToken -> (string)

  

  When a response is generated, if there is more data to be listed, this parameter is present in the response and contains the value to use for the **nextToken** parameter in a subsequent pagination request. If there is no more data to be listed, this parameter is set to null.

  

  

