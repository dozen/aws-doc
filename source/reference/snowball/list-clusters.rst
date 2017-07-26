[ :ref:`aws <cli:aws>` . :ref:`snowball <cli:aws snowball>` ]

.. _cli:aws snowball list-clusters:


*************
list-clusters
*************



===========
Description
===========



Returns an array of ``ClusterListEntry`` objects of the specified length. Each ``ClusterListEntry`` object contains a cluster's state, a cluster's ID, and other important status information.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/snowball-2016-06-30/ListClusters>`_


========
Synopsis
========

::

    list-clusters
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--max-results`` (integer)


  The number of ``ClusterListEntry`` objects to return.

  

``--next-token`` (string)


  HTTP requests are stateless. To identify what object comes "next" in the list of ``ClusterListEntry`` objects, you have the option of specifying ``NextToken`` as the starting point for your returned list.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ClusterListEntries -> (list)

  

  Each ``ClusterListEntry`` object contains a cluster's state, a cluster's ID, and other important status information.

  

  (structure)

    

    Contains a cluster's state, a cluster's ID, and other important information.

    

    ClusterId -> (string)

      

      The 39-character ID for the cluster that you want to list, for example ``CID123e4567-e89b-12d3-a456-426655440000`` .

      

      

    ClusterState -> (string)

      

      The current state of this cluster. For information about the state of a specific node, see  JobListEntry$JobState .

      

      

    CreationDate -> (timestamp)

      

      The creation date for this cluster.

      

      

    Description -> (string)

      

      Defines an optional description of the cluster, for example ``Environmental Data Cluster-01`` .

      

      

    

  

NextToken -> (string)

  

  HTTP requests are stateless. If you use the automatically generated ``NextToken`` value in your next ``ClusterListEntry`` call, your list of returned clusters will start from this point in the array.

  

  

