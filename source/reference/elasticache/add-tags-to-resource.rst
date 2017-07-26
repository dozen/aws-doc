[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache add-tags-to-resource:


********************
add-tags-to-resource
********************



===========
Description
===========



Adds up to 50 cost allocation tags to the named resource. A cost allocation tag is a key-value pair where the key and value are case-sensitive. You can use cost allocation tags to categorize and track your AWS costs.

 

When you apply tags to your ElastiCache resources, AWS generates a cost allocation report as a comma-separated value (CSV) file with your usage and costs aggregated by your tags. You can apply tags that represent business categories (such as cost centers, application names, or owners) to organize your costs across multiple services. For more information, see `Using Cost Allocation Tags in Amazon ElastiCache <http://docs.aws.amazon.com/AmazonElastiCache/latest/UserGuide/Tagging.html>`_ in the *ElastiCache User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticache-2015-02-02/AddTagsToResource>`_


========
Synopsis
========

::

    add-tags-to-resource
  --resource-name <value>
  --tags <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-name`` (string)


  The Amazon Resource Name (ARN) of the resource to which the tags are to be added, for example ``arn:aws:elasticache:us-west-2:0123456789:cluster:myCluster`` or ``arn:aws:elasticache:us-west-2:0123456789:snapshot:mySnapshot`` .

   

  For more information about ARNs, see `Amazon Resource Names (ARNs) and AWS Service Namespaces <http://docs.aws.amazon.com/general/latest/gr/aws-arns-and-namespaces.html>`_ .

  

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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

TagList -> (list)

  

  A list of cost allocation tags as key-value pairs.

  

  (structure)

    

    A cost allocation Tag that can be added to an ElastiCache cluster or replication group. Tags are composed of a Key/Value pair. A tag with a null Value is permitted.

    

    Key -> (string)

      

      The key for the tag. May not be null.

      

      

    Value -> (string)

      

      The tag's value. May be null.

      

      

    

  

