[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache create-cache-parameter-group:


****************************
create-cache-parameter-group
****************************



===========
Description
===========



The *create-cache-parameter-group* action creates a new cache parameter group. A cache parameter group is a collection of parameters that you apply to all of the nodes in a cache cluster.



========
Synopsis
========

::

    create-cache-parameter-group
  --cache-parameter-group-name <value>
  --cache-parameter-group-family <value>
  --description <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cache-parameter-group-name`` (string)


  A user-specified name for the cache parameter group.

  

``--cache-parameter-group-family`` (string)


  The name of the cache parameter group family the cache parameter group can be used with.

   

  Valid values are: ``memcached1.4`` | ``redis2.6`` | ``redis2.8`` 

  

``--description`` (string)


  A user-specified description for the cache parameter group.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

CacheParameterGroup -> (structure)

  

  Represents the output of a *create-cache-parameter-group* action.

  

  CacheParameterGroupName -> (string)

    

    The name of the cache parameter group.

    

    

  CacheParameterGroupFamily -> (string)

    

    The name of the cache parameter group family that this cache parameter group is compatible with.

    

    

  Description -> (string)

    

    The description for this cache parameter group.

    

    

  

