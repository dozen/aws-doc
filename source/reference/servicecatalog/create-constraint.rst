[ :ref:`aws <cli:aws>` . :ref:`servicecatalog <cli:aws servicecatalog>` ]

.. _cli:aws servicecatalog create-constraint:


*****************
create-constraint
*****************



===========
Description
===========



Creates a new constraint. For more information, see `Using Constraints <http://docs.aws.amazon.com/servicecatalog/latest/adminguide/constraints.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/servicecatalog-2015-12-10/CreateConstraint>`_


========
Synopsis
========

::

    create-constraint
  [--accept-language <value>]
  --portfolio-id <value>
  --product-id <value>
  --parameters <value>
  --type <value>
  [--description <value>]
  --idempotency-token <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--accept-language`` (string)


  The language code to use for this operation. Supported language codes are as follows:

   

  "en" (English)

   

  "jp" (Japanese)

   

  "zh" (Chinese)

   

  If no code is specified, "en" is used as the default.

  

``--portfolio-id`` (string)


  The portfolio identifier.

  

``--product-id`` (string)


  The product identifier.

  

``--parameters`` (string)


  The constraint parameters. Expected values vary depending on which **Type** is specified. For examples, see the bottom of this topic.

   

  For Type ``LAUNCH`` , the ``RoleArn`` property is required. 

   

  For Type ``NOTIFICATION`` , the ``NotificationArns`` property is required.

   

  For Type ``TEMPLATE`` , the ``Rules`` property is required.

  

``--type`` (string)


  The type of the constraint. Case-sensitive valid values are: ``LAUNCH`` , ``NOTIFICATION`` , or ``TEMPLATE`` . 

  

``--description`` (string)


  The text description of the constraint.

  

``--idempotency-token`` (string)


  A token to disambiguate duplicate requests. You can create multiple resources using the same input in multiple requests, provided that you also specify a different idempotency token for each request.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ConstraintDetail -> (structure)

  

  The resulting detailed constraint information.

  

  ConstraintId -> (string)

    

    The identifier of the constraint.

    

    

  Type -> (string)

    

    The type of the constraint.

    

    

  Description -> (string)

    

    The text description of the constraint.

    

    

  Owner -> (string)

    

    The owner of the constraint.

    

    

  

ConstraintParameters -> (string)

  

  The resulting constraint parameters.

  

  

Status -> (string)

  

  The status of the current request.

  

  

