[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector list-assessment-run-agents:


**************************
list-assessment-run-agents
**************************



===========
Description
===========



Lists the agents of the assessment runs that are specified by the ARNs of the assessment runs.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/inspector-2016-02-16/ListAssessmentRunAgents>`_


========
Synopsis
========

::

    list-assessment-run-agents
  --assessment-run-arn <value>
  [--filter <value>]
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--assessment-run-arn`` (string)


  The ARN that specifies the assessment run whose agents you want to list.

  

``--filter`` (structure)


  You can use this parameter to specify a subset of data to be included in the action's response.

   

  For a record to match a filter, all specified filter attributes must match. When multiple values are specified for a filter attribute, any of the values can match.

  



Shorthand Syntax::

    agentHealths=string,string,agentHealthCodes=string,string




JSON Syntax::

  {
    "agentHealths": ["HEALTHY"|"UNHEALTHY", ...],
    "agentHealthCodes": ["IDLE"|"RUNNING"|"SHUTDOWN"|"UNHEALTHY"|"THROTTLED"|"UNKNOWN", ...]
  }



``--next-token`` (string)


  You can use this parameter when paginating results. Set the value of this parameter to null on your first call to the **list-assessment-run-agents** action. Subsequent calls to the action fill **nextToken** in the request with the value of **NextToken** from the previous response to continue listing data.

  

``--max-results`` (integer)


  You can use this parameter to indicate the maximum number of items that you want in the response. The default value is 10. The maximum value is 500.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To list assessment run agents**

The following ``list-assessment-run-agents`` command lists the agents of the assessment run with the ARN of ``arn:aws:inspector:us-west-2:123456789012:target/0-0kFIPusq/template/0-4r1V2mAw/run/0-MKkpXXPE``::

  aws inspector list-assessment-run-agents --assessment-run-arn arn:aws:inspector:us-west-2:123456789012:target/0-0kFIPusq/template/0-4r1V2mAw/run/0-MKkpXXPE

Output::

{
	 "assessmentRunAgents": [
	   {
		 "agentHealth": "HEALTHY",
		 "agentHealthCode": "HEALTHY",
		 "agentId": "i-49113b93",
		 "assessmentRunArn": "arn:aws:inspector:us-west-2:123456789012:target/0-0kFIPusq/template/0-4r1V2mAw/run/0-MKkpXXPE",
		 "telemetryMetadata": [
		   {
			 "count": 2,
			 "dataSize": 345,
			 "messageType": "InspectorDuplicateProcess"
		   },
		   {
			 "count": 3,
			 "dataSize": 255,
			 "messageType": "InspectorTimeEventMsg"
		   },
		   {
			 "count": 4,
			 "dataSize": 1082,
			 "messageType": "InspectorNetworkInterface"
		   },
		   {
			 "count": 2,
			 "dataSize": 349,
			 "messageType": "InspectorDnsEntry"
		   },
		   {
			 "count": 11,
			 "dataSize": 2514,
			 "messageType": "InspectorDirectoryInfoMsg"
		   },
		   {
			 "count": 1,
			 "dataSize": 179,
			 "messageType": "InspectorTcpV6ListeningPort"
		   },
		   {
			 "count": 101,
			 "dataSize": 10949,
			 "messageType": "InspectorTerminal"
		   },
		   {
			 "count": 26,
			 "dataSize": 5916,
			 "messageType": "InspectorUser"
		   },
		   {
			 "count": 282,
			 "dataSize": 32148,
			 "messageType": "InspectorDynamicallyLoadedCodeModule"
		   },
		   {
			 "count": 18,
			 "dataSize": 10172,
			 "messageType": "InspectorCreateProcess"
		   },
		   {
			 "count": 3,
			 "dataSize": 8001,
			 "messageType": "InspectorProcessPerformance"
		   },
		   {
			 "count": 1,
			 "dataSize": 360,
			 "messageType": "InspectorOperatingSystem"
		   },
		   {
			 "count": 6,
			 "dataSize": 546,
			 "messageType": "InspectorStopProcess"
		   },
		   {
			 "count": 1,
			 "dataSize": 1553,
			 "messageType": "InspectorInstanceMetaData"
		   },
		   {
			 "count": 2,
			 "dataSize": 434,
			 "messageType": "InspectorTcpV4Connection"
		   },
		   {
			 "count": 474,
			 "dataSize": 2960322,
			 "messageType": "InspectorPackageInfo"
		   },
		   {
			 "count": 3,
			 "dataSize": 2235,
			 "messageType": "InspectorSystemPerformance"
		   },
		   {
			 "count": 105,
			 "dataSize": 46048,
			 "messageType": "InspectorCodeModule"
		   },
		   {
			 "count": 1,
			 "dataSize": 182,
			 "messageType": "InspectorUdpV6ListeningPort"
		   },
		   {
			 "count": 2,
			 "dataSize": 371,
			 "messageType": "InspectorUdpV4ListeningPort"
		   },
		   {
			 "count": 18,
			 "dataSize": 8362,
			 "messageType": "InspectorKernelModule"
		   },
		   {
			 "count": 29,
			 "dataSize": 48788,
			 "messageType": "InspectorConfigurationInfo"
		   },
		   {
			 "count": 1,
			 "dataSize": 79,
			 "messageType": "InspectorMonitoringStart"
		   },
		   {
			 "count": 5,
			 "dataSize": 0,
			 "messageType": "InspectorSplitMsgBegin"
		   },
		   {
			 "count": 51,
			 "dataSize": 4593,
			 "messageType": "InspectorGroup"
		   },
		   {
			 "count": 1,
			 "dataSize": 184,
			 "messageType": "InspectorTcpV4ListeningPort"
		   },
		   {
			 "count": 1159,
			 "dataSize": 3146579,
			 "messageType": "Total"
		   },
		   {
			 "count": 5,
			 "dataSize": 0,
			 "messageType": "InspectorSplitMsgEnd"
		   },
		   {
			 "count": 1,
			 "dataSize": 612,
			 "messageType": "InspectorLoadImageInProcess"
		   }
		 ]
	   }
	 ]
	}

For more information, see `AWS Agents`_ in the *Amazon Inspector* guide.

.. _`AWS Agents`: https://docs.aws.amazon.com/inspector/latest/userguide/inspector_agents.html



======
Output
======

assessmentRunAgents -> (list)

  

  A list of ARNs that specifies the agents returned by the action.

  

  (structure)

    

    Contains information about an Amazon Inspector agent. This data type is used as a response element in the  list-assessment-run-agents action.

    

    agentId -> (string)

      

      The AWS account of the EC2 instance where the agent is installed.

      

      

    assessmentRunArn -> (string)

      

      The ARN of the assessment run that is associated with the agent.

      

      

    agentHealth -> (string)

      

      The current health state of the agent.

      

      

    agentHealthCode -> (string)

      

      The detailed health state of the agent.

      

      

    agentHealthDetails -> (string)

      

      The description for the agent health code.

      

      

    autoScalingGroup -> (string)

      

      The Auto Scaling group of the EC2 instance that is specified by the agent ID.

      

      

    telemetryMetadata -> (list)

      

      The Amazon Inspector application data metrics that are collected by the agent.

      

      (structure)

        

        The metadata about the Amazon Inspector application data metrics collected by the agent. This data type is used as the response element in the  get-telemetry-metadata action.

        

        messageType -> (string)

          

          A specific type of behavioral data that is collected by the agent.

          

          

        count -> (long)

          

          The count of messages that the agent sends to the Amazon Inspector service.

          

          

        dataSize -> (long)

          

          The data size of messages that the agent sends to the Amazon Inspector service.

          

          

        

      

    

  

nextToken -> (string)

  

  When a response is generated, if there is more data to be listed, this parameter is present in the response and contains the value to use for the **nextToken** parameter in a subsequent pagination request. If there is no more data to be listed, this parameter is set to null.

  

  

