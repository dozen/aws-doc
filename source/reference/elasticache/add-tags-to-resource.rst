[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache add-tags-to-resource:


********************
add-tags-to-resource
********************



===========
Description
===========



The *add-tags-to-resource* action adds up to 10 cost allocation tags to the named resource. A *cost allocation tag* is a key-value pair where the key and value are case-sensitive. Cost allocation tags can be used to categorize and track your AWS costs.

 

When you apply tags to your ElastiCache resources, AWS generates a cost allocation report as a comma-separated value (CSV) file with your usage and costs aggregated by your tags. You can apply tags that represent business categories (such as cost centers, application names, or owners) to organize your costs across multiple services. For more information, see `Using Cost Allocation Tags in Amazon ElastiCache`_ .



========
Synopsis
========

::

    add-tags-to-resource
  --resource-name <value>
  --tags <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--resource-name`` (string)


  The name of the resource to which the tags are to be added, for example ``arn:aws:elasticache:us-west-2:0123456789:cluster:myCluster`` .

  

``--tags`` (list)


  A list of cost allocation tags to be added to this resource. A tag is a key-value pair. A tag key must be accompanied by a tag value.

  



Shorthand Syntax::

    Key=string,Value=string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Value": "string"
    }
    ...
  ]



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

      

      

    

  



.. _Using Cost Allocation Tags in Amazon ElastiCache: http://docs.aws.amazon.com/AmazonElastiCache/latest/UserGuide/Tagging.html
