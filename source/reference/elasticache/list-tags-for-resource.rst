[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache list-tags-for-resource:


**********************
list-tags-for-resource
**********************



===========
Description
===========



The *list-tags-for-resource* action lists all cost allocation tags currently on the named resource. A *cost allocation tag* is a key-value pair where the key is case-sensitive and the value is optional. Cost allocation tags can be used to categorize and track your AWS costs.

 

You can have a maximum of 10 cost allocation tags on an ElastiCache resource. For more information, see `Using Cost Allocation Tags in Amazon ElastiCache`_ .



========
Synopsis
========

::

    list-tags-for-resource
  --resource-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--resource-name`` (string)


  The name of the resource for which you want the list of tags, for example ``arn:aws:elasticache:us-west-2:0123456789:cluster:myCluster`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

TagList -> (list)

  

  A list of cost allocation tags as key-value pairs. 

  

  (structure)

    

    A cost allocation Tag that can be added to an ElastiCache cluster or replication group. Tags are composed of a Key/Value pair. A tag with a null Value is permitted.

    

    Key -> (string)

      

      The key for the tag.

      

      

    Value -> (string)

      

      The tag's value. May not be null.

      

      

    

  



.. _Using Cost Allocation Tags in Amazon ElastiCache: http://docs.aws.amazon.com/AmazonElastiCache/latest/UserGuide/BestPractices.html
