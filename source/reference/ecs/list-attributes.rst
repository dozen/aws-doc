[ :ref:`aws <cli:aws>` . :ref:`ecs <cli:aws ecs>` ]

.. _cli:aws ecs list-attributes:


***************
list-attributes
***************



===========
Description
===========



Lists the attributes for Amazon ECS resources within a specified target type and cluster. When you specify a target type and cluster, ``list-attributes`` returns a list of attribute objects, one for each attribute on each resource. You can filter the list of results to a single attribute name to only return results that have that name. You can also filter the results by attribute name and value, for example, to see which container instances in a cluster are running a Linux AMI (``ecs.os-type=linux`` ). 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ecs-2014-11-13/ListAttributes>`_


========
Synopsis
========

::

    list-attributes
  [--cluster <value>]
  --target-type <value>
  [--attribute-name <value>]
  [--attribute-value <value>]
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cluster`` (string)


  The short name or full Amazon Resource Name (ARN) of the cluster to list attributes. If you do not specify a cluster, the default cluster is assumed.

  

``--target-type`` (string)


  The type of the target with which to list attributes.

  

  Possible values:

  
  *   ``container-instance``

  

  

``--attribute-name`` (string)


  The name of the attribute with which to filter the results. 

  

``--attribute-value`` (string)


  The value of the attribute with which to filter results. You must also specify an attribute name to use this parameter.

  

``--next-token`` (string)


  The ``nextToken`` value returned from a previous paginated ``list-attributes`` request where ``maxResults`` was used and the results exceeded the value of that parameter. Pagination continues from the end of the previous results that returned the ``nextToken`` value. This value is ``null`` when there are no more results to return.

   

  .. note::

     

    This token should be treated as an opaque identifier that is only used to retrieve the next items in a list and not for other programmatic purposes.

     

  

``--max-results`` (integer)


  The maximum number of cluster results returned by ``list-attributes`` in paginated output. When this parameter is used, ``list-attributes`` only returns ``maxResults`` results in a single page along with a ``nextToken`` response element. The remaining results of the initial request can be seen by sending another ``list-attributes`` request with the returned ``nextToken`` value. This value can be between 1 and 100. If this parameter is not used, then ``list-attributes`` returns up to 100 results and a ``nextToken`` value if applicable.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

attributes -> (list)

  

  A list of attribute objects that meet the criteria of the request.

  

  (structure)

    

    An attribute is a name-value pair associated with an Amazon ECS object. Attributes enable you to extend the Amazon ECS data model by adding custom metadata to your resources. For more information, see `Attributes <http://docs.aws.amazon.com/AmazonECS/latest/developerguide/task-placement-constraints.html#attributes>`_ in the *Amazon EC2 Container Service Developer Guide* .

    

    name -> (string)

      

      The name of the attribute. Up to 128 letters (uppercase and lowercase), numbers, hyphens, underscores, and periods are allowed.

      

      

    value -> (string)

      

      The value of the attribute. Up to 128 letters (uppercase and lowercase), numbers, hyphens, underscores, periods, at signs (@), forward slashes, colons, and spaces are allowed.

      

      

    targetType -> (string)

      

      The type of the target with which to attach the attribute. This parameter is required if you use the short form ID for a resource instead of the full Amazon Resource Name (ARN).

      

      

    targetId -> (string)

      

      The ID of the target. You can specify the short form ID for a resource or the full Amazon Resource Name (ARN).

      

      

    

  

nextToken -> (string)

  

  The ``nextToken`` value to include in a future ``list-attributes`` request. When the results of a ``list-attributes`` request exceed ``maxResults`` , this value can be used to retrieve the next page of results. This value is ``null`` when there are no more results to return.

  

  

