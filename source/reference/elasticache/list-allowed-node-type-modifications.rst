[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache list-allowed-node-type-modifications:


************************************
list-allowed-node-type-modifications
************************************



===========
Description
===========



Lists all available node types that you can scale your Redis cluster's or replication group's current node type up to.

 

When you use the ``modify-cache-cluster`` or ``modify-replication-group`` operations to scale up your cluster or replication group, the value of the ``CacheNodeType`` parameter must be one of the node types returned by this operation.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticache-2015-02-02/ListAllowedNodeTypeModifications>`_


========
Synopsis
========

::

    list-allowed-node-type-modifications
  [--cache-cluster-id <value>]
  [--replication-group-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cache-cluster-id`` (string)


  The name of the cache cluster you want to scale up to a larger node instanced type. ElastiCache uses the cluster id to identify the current node type of this cluster and from that to create a list of node types you can scale up to.

   

  .. warning::

     

    You must provide a value for either the ``CacheClusterId`` or the ``ReplicationGroupId`` .

     

  

``--replication-group-id`` (string)


  The name of the replication group want to scale up to a larger node type. ElastiCache uses the replication group id to identify the current node type being used by this replication group, and from that to create a list of node types you can scale up to.

   

  .. warning::

     

    You must provide a value for either the ``CacheClusterId`` or the ``ReplicationGroupId`` .

     

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ScaleUpModifications -> (list)

  

  A string list, each element of which specifies a cache node type which you can use to scale your cache cluster or replication group.

   

  When scaling up a Redis cluster or replication group using ``modify-cache-cluster`` or ``modify-replication-group`` , use a value from this list for the ``CacheNodeType`` parameter.

  

  (string)

    

    

  

