[ :ref:`aws <cli:aws>` . :ref:`discovery <cli:aws discovery>` ]

.. _cli:aws discovery list-server-neighbors:


*********************
list-server-neighbors
*********************



===========
Description
===========



Retrieves a list of servers that are one network hop away from a specified server.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/discovery-2015-11-01/ListServerNeighbors>`_


========
Synopsis
========

::

    list-server-neighbors
  --configuration-id <value>
  [--port-information-needed | --no-port-information-needed]
  [--neighbor-configuration-ids <value>]
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--configuration-id`` (string)


  Configuration ID of the server for which neighbors are being listed.

  

``--port-information-needed`` | ``--no-port-information-needed`` (boolean)


  Flag to indicate if port and protocol information is needed as part of the response.

  

``--neighbor-configuration-ids`` (list)


  List of configuration IDs to test for one-hop-away.

  



Syntax::

  "string" "string" ...



``--max-results`` (integer)


  Maximum number of results to return in a single page of output.

  

``--next-token`` (string)


  Token to retrieve the next set of results. For example, if you previously specified 100 IDs for ``ListServerNeighborsRequest$neighborConfigurationIds`` but set ``ListServerNeighborsRequest$maxResults`` to 10, you received a set of 10 results along with a token. Use that token in this query to get the next set of 10.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

neighbors -> (list)

  

  List of distinct servers that are one hop away from the given server.

  

  (structure)

    

    Details about neighboring servers.

    

    sourceServerId -> (string)

      

      The ID of the server that opened the network connection.

      

      

    destinationServerId -> (string)

      

      The ID of the server that accepted the network connection.

      

      

    destinationPort -> (integer)

      

      The destination network port for the connection.

      

      

    transportProtocol -> (string)

      

      The network protocol used for the connection.

      

      

    connectionsCount -> (long)

      

      The number of open network connections with the neighboring server.

      

      

    

  

nextToken -> (string)

  

  Token to retrieve the next set of results. For example, if you specified 100 IDs for ``ListServerNeighborsRequest$neighborConfigurationIds`` but set ``ListServerNeighborsRequest$maxResults`` to 10, you received a set of 10 results along with this token. Use this token in the next query to retrieve the next set of 10.

  

  

knownDependencyCount -> (long)

  

  Count of distinct servers that are one hop away from the given server.

  

  

