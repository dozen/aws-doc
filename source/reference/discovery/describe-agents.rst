[ :ref:`aws <cli:aws>` . :ref:`discovery <cli:aws discovery>` ]

.. _cli:aws discovery describe-agents:


***************
describe-agents
***************



===========
Description
===========



Lists agents or the Connector by ID or lists all agents/Connectors associated with your user account if you did not specify an ID.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/discovery-2015-11-01/DescribeAgents>`_


========
Synopsis
========

::

    describe-agents
  [--agent-ids <value>]
  [--filters <value>]
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--agent-ids`` (list)


  The agent or the Connector IDs for which you want information. If you specify no IDs, the system returns information about all agents/Connectors associated with your AWS user account.

  



Syntax::

  "string" "string" ...



``--filters`` (list)


  You can filter the request using various logical operators and a *key* -*value* format. For example: 

   

   ``{"key": "collectionStatus", "value": "STARTED"}``  

  



Shorthand Syntax::

    name=string,values=string,string,condition=string ...




JSON Syntax::

  [
    {
      "name": "string",
      "values": ["string", ...],
      "condition": "string"
    }
    ...
  ]



``--max-results`` (integer)


  The total number of agents/Connectors to return in a single page of output. The maximum value is 100.

  

``--next-token`` (string)


  Token to retrieve the next set of results. For example, if you previously specified 100 IDs for ``DescribeAgentsRequest$agentIds`` but set ``DescribeAgentsRequest$maxResults`` to 10, you received a set of 10 results along with a token. Use that token in this query to get the next set of 10.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**Describe agents with specified collectionStatus states**

This example command describes collection agents with collection status of "STARTED" or "STOPPED".

Command::

  aws discovery describe-agents --filters name="collectionStatus",values="STARTED","STOPPED",condition="EQUALS" --max-results 3

Output::

  {
         "Snapshots": [
  	{
              "version": "1.0.40.0",
              "agentType": "EC2",
              "hostName": "ip-172-31-40-234",
              "collectionStatus": "STOPPED",
              "agentNetworkInfoList": [
                  {
                      "macAddress": "06:b5:97:14:fc:0d",
                      "ipAddress": "172.31.40.234"
                  }
              ],
              "health": "UNKNOWN",
              "agentId": "i-003305c02a776e883",
              "registeredTime": "2016-12-09T19:05:06Z",
              "lastHealthPingTime": "2016-12-09T19:05:10Z"
          },
          {
              "version": "1.0.40.0",
              "agentType": "EC2",
              "hostName": "ip-172-31-39-64",
              "collectionStatus": "STARTED",
              "agentNetworkInfoList": [
                  {
                      "macAddress": "06:a1:0e:c7:b2:73",
                      "ipAddress": "172.31.39.64"
                  }
              ],
              "health": "SHUTDOWN",
              "agentId": "i-003a5e5e2b36cf8bd",
              "registeredTime": "2016-11-16T16:36:25Z",
              "lastHealthPingTime": "2016-11-16T16:47:37Z"
          }
      ]
  }


======
Output
======

agentsInfo -> (list)

  

  Lists agents or the Connector by ID or lists all agents/Connectors associated with your user account if you did not specify an agent/Connector ID. The output includes agent/Connector IDs, IP addresses, media access control (MAC) addresses, agent/Connector health, host name where the agent/Connector resides, and the version number of each agent/Connector.

  

  (structure)

    

    Information about agents or connectors associated with the user’s AWS account. Information includes agent or connector IDs, IP addresses, media access control (MAC) addresses, agent or connector health, hostname where the agent or connector resides, and agent version for each agent.

    

    agentId -> (string)

      

      The agent or connector ID.

      

      

    hostName -> (string)

      

      The name of the host where the agent or connector resides. The host can be a server or virtual machine.

      

      

    agentNetworkInfoList -> (list)

      

      Network details about the host where the agent or connector resides.

      

      (structure)

        

        Network details about the host where the agent/connector resides.

        

        ipAddress -> (string)

          

          The IP address for the host where the agent/connector resides.

          

          

        macAddress -> (string)

          

          The MAC address for the host where the agent/connector resides.

          

          

        

      

    connectorId -> (string)

      

      The ID of the connector.

      

      

    version -> (string)

      

      The agent or connector version.

      

      

    health -> (string)

      

      The health of the agent or connector.

      

      

    lastHealthPingTime -> (string)

      

      Time since agent or connector health was reported.

      

      

    collectionStatus -> (string)

      

      Status of the collection process for an agent or connector.

      

      

    agentType -> (string)

      

      Type of agent.

      

      

    registeredTime -> (string)

      

      Agent's first registration timestamp in UTC.

      

      

    

  

nextToken -> (string)

  

  Token to retrieve the next set of results. For example, if you specified 100 IDs for ``DescribeAgentsRequest$agentIds`` but set ``DescribeAgentsRequest$maxResults`` to 10, you received a set of 10 results along with this token. Use this token in the next query to retrieve the next set of 10.

  

  

