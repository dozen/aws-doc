[ :ref:`aws <cli:aws>` . :ref:`discovery <cli:aws discovery>` ]

.. _cli:aws discovery stop-data-collection-by-agent-ids:


*********************************
stop-data-collection-by-agent-ids
*********************************



===========
Description
===========



Instructs the specified agents or connectors to stop collecting data.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/discovery-2015-11-01/StopDataCollectionByAgentIds>`_


========
Synopsis
========

::

    stop-data-collection-by-agent-ids
  --agent-ids <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--agent-ids`` (list)


  The IDs of the agents or connectors from which to stop collecting data.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

agentsConfigurationStatus -> (list)

  

  Information about the agents or connector that were instructed to stop collecting data. Information includes the agent/connector ID, a description of the operation performed, and whether the agent/connector configuration was updated.

  

  (structure)

    

    Information about agents or connectors that were instructed to start collecting data. Information includes the agent/connector ID, a description of the operation, and whether the agent/connector configuration was updated.

    

    agentId -> (string)

      

      The agent/connector ID.

      

      

    operationSucceeded -> (boolean)

      

      Information about the status of the ``StartDataCollection`` and ``StopDataCollection`` operations. The system has recorded the data collection operation. The agent/connector receives this command the next time it polls for a new command. 

      

      

    description -> (string)

      

      A description of the operation performed.

      

      

    

  

