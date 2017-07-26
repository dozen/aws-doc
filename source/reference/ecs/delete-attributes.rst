[ :ref:`aws <cli:aws>` . :ref:`ecs <cli:aws ecs>` ]

.. _cli:aws ecs delete-attributes:


*****************
delete-attributes
*****************



===========
Description
===========



Deletes one or more custom attributes from an Amazon ECS resource.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ecs-2014-11-13/DeleteAttributes>`_


========
Synopsis
========

::

    delete-attributes
  [--cluster <value>]
  --attributes <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cluster`` (string)


  The short name or full Amazon Resource Name (ARN) of the cluster that contains the resource to delete attributes. If you do not specify a cluster, the default cluster is assumed.

  

``--attributes`` (list)


  The attributes to delete from your resource. You can specify up to 10 attributes per request. For custom attributes, specify the attribute name and target ID, but do not specify the value. If you specify the target ID using the short form, you must also specify the target type.

  



Shorthand Syntax::

    name=string,value=string,targetType=string,targetId=string ...




JSON Syntax::

  [
    {
      "name": "string",
      "value": "string",
      "targetType": "container-instance",
      "targetId": "string"
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

attributes -> (list)

  

  A list of attribute objects that were successfully deleted from your resource.

  

  (structure)

    

    An attribute is a name-value pair associated with an Amazon ECS object. attributes enable you to extend the Amazon ECS data model by adding custom metadata to your resources. For more information, see `attributes <http://docs.aws.amazon.com/AmazonECS/latest/developerguide/task-placement-constraints.html#attributes>`_ in the *Amazon EC2 Container Service Developer Guide* .

    

    name -> (string)

      

      The name of the attribute. Up to 128 letters (uppercase and lowercase), numbers, hyphens, underscores, and periods are allowed.

      

      

    value -> (string)

      

      The value of the attribute. Up to 128 letters (uppercase and lowercase), numbers, hyphens, underscores, periods, at signs (@), forward slashes, colons, and spaces are allowed.

      

      

    targetType -> (string)

      

      The type of the target with which to attach the attribute. This parameter is required if you use the short form ID for a resource instead of the full Amazon Resource Name (ARN).

      

      

    targetId -> (string)

      

      The ID of the target. You can specify the short form ID for a resource or the full Amazon Resource Name (ARN).

      

      

    

  

