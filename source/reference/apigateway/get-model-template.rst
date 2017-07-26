[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway get-model-template:


******************
get-model-template
******************



===========
Description
===========



Generates a sample mapping template that can be used to transform a payload into the structure of a model.



========
Synopsis
========

::

    get-model-template
  --rest-api-id <value>
  --model-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--rest-api-id`` (string)


  The ID of the  RestApi under which the model exists.

  

``--model-name`` (string)


  The name of the model for which to generate a template.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

value -> (string)

  

  The Apache `Velocity Template Language (VTL)`_ template content used for the template resource.

  

  



.. _Velocity Template Language (VTL): http://velocity.apache.org/engine/devel/vtl-reference-guide.html
