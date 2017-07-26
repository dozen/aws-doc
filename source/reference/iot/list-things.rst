[ :ref:`aws <cli:aws>` . :ref:`iot <cli:aws iot>` ]

.. _cli:aws iot list-things:


***********
list-things
***********



===========
Description
===========



Lists your things. You can pass an attribute-name and/or attribute-value to filter your things. For example: "ListThings where AttributeName=Color and AttributeValue=Red"



========
Synopsis
========

::

    list-things
  [--next-token <value>]
  [--max-results <value>]
  [--attribute-name <value>]
  [--attribute-value <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--next-token`` (string)


  The token for the next value.

  

``--max-results`` (integer)


  The maximum number of results.

  

``--attribute-name`` (string)


  The attribute name.

  

``--attribute-value`` (string)


  The attribute value.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

things -> (list)

  

  The things.

  

  (structure)

    

    Describes a thing attribute.

    

    thingName -> (string)

      

      The name of the thing.

      

      

    attributes -> (map)

      

      The attributes.

      

      key -> (string)

        

        

      value -> (string)

        

        

      

    

  

nextToken -> (string)

  

  A token used to retrieve the next value.

  

  

