[ :ref:`aws <cli:aws>` . :ref:`discovery <cli:aws discovery>` ]

.. _cli:aws discovery get-discovery-summary:


*********************
get-discovery-summary
*********************



===========
Description
===========



Retrieves a short summary of discovered assets.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/discovery-2015-11-01/GetDiscoverySummary>`_


========
Synopsis
========

::

    get-discovery-summary
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

servers -> (long)

  

  The number of servers discovered.

  

  

applications -> (long)

  

  The number of applications discovered.

  

  

serversMappedToApplications -> (long)

  

  The number of servers mapped to applications.

  

  

serversMappedtoTags -> (long)

  

  The number of servers mapped to tags.

  

  

agentSummary -> (structure)

  

  Details about discovered agents, including agent status and health.

  

  activeAgents -> (integer)

    

    Number of active discovery agents.

    

    

  healthyAgents -> (integer)

    

    Number of healthy discovery agents

    

    

  blackListedAgents -> (integer)

    

    Number of blacklisted discovery agents.

    

    

  shutdownAgents -> (integer)

    

    Number of discovery agents with status SHUTDOWN.

    

    

  unhealthyAgents -> (integer)

    

    Number of unhealthy discovery agents.

    

    

  totalAgents -> (integer)

    

    Total number of discovery agents.

    

    

  unknownAgents -> (integer)

    

    Number of unknown discovery agents.

    

    

  

connectorSummary -> (structure)

  

  Details about discovered connectors, including connector status and health.

  

  activeConnectors -> (integer)

    

    Number of active discovery connectors.

    

    

  healthyConnectors -> (integer)

    

    Number of healthy discovery connectors.

    

    

  blackListedConnectors -> (integer)

    

    Number of blacklisted discovery connectors.

    

    

  shutdownConnectors -> (integer)

    

    Number of discovery connectors with status SHUTDOWN,

    

    

  unhealthyConnectors -> (integer)

    

    Number of unhealthy discovery connectors.

    

    

  totalConnectors -> (integer)

    

    Total number of discovery connectors.

    

    

  unknownConnectors -> (integer)

    

    Number of unknown discovery connectors.

    

    

  

