[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache create-cache-parameter-group:


****************************
create-cache-parameter-group
****************************



===========
Description
===========



Creates a new Amazon ElastiCache cache parameter group. An ElastiCache cache parameter group is a collection of parameters and their values that are applied to all of the nodes in any cache cluster or replication group using the CacheParameterGroup.

 

A newly created CacheParameterGroup is an exact duplicate of the default parameter group for the CacheParameterGroupFamily. To customize the newly created CacheParameterGroup you can change the values of specific parameters. For more information, see:

 

 
* `modify-cache-parameter-group <http://docs.aws.amazon.com/AmazonElastiCache/latest/APIReference/API_ModifyCacheParameterGroup.html>`_ in the ElastiCache API Reference. 
 
* `Parameters and Parameter Groups <http://docs.aws.amazon.com/AmazonElastiCache/latest/UserGuide/ParameterGroups.html>`_ in the ElastiCache User Guide. 
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticache-2015-02-02/CreateCacheParameterGroup>`_


========
Synopsis
========

::

    create-cache-parameter-group
  --cache-parameter-group-name <value>
  --cache-parameter-group-family <value>
  --description <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cache-parameter-group-name`` (string)


  A user-specified name for the cache parameter group.

  

``--cache-parameter-group-family`` (string)


  The name of the cache parameter group family that the cache parameter group can be used with.

   

  Valid values are: ``memcached1.4`` | ``redis2.6`` | ``redis2.8`` | ``redis3.2``  

  

``--description`` (string)


  A user-specified description for the cache parameter group.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

CacheParameterGroup -> (structure)

  

  Represents the output of a ``create-cache-parameter-group`` operation.

  

  CacheParameterGroupName -> (string)

    

    The name of the cache parameter group.

    

    

  CacheParameterGroupFamily -> (string)

    

    The name of the cache parameter group family that this cache parameter group is compatible with.

     

    Valid values are: ``memcached1.4`` | ``redis2.6`` | ``redis2.8`` | ``redis3.2``  

    

    

  Description -> (string)

    

    The description for this cache parameter group.

    

    

  

