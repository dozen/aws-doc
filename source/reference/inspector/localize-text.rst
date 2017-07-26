[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector localize-text:


*************
localize-text
*************



===========
Description
===========



Translates a textual identifier into a user-readable text in a specified locale.



========
Synopsis
========

::

    localize-text
  --localized-texts <value>
  --locale <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--localized-texts`` (list)


  A list of textual identifiers.

  



Shorthand Syntax::

    key={facility=string,id=string},parameters=[{name=string,value=string},{name=string,value=string}] ...




JSON Syntax::

  [
    {
      "key": {
        "facility": "string",
        "id": "string"
      },
      "parameters": [
        {
          "name": "string",
          "value": "string"
        }
        ...
      ]
    }
    ...
  ]



``--locale`` (string)


  The locale that you want to translate a textual identifier into.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

message -> (string)

  

  Confirmation details of the action performed.

  

  

results -> (list)

  

  The resulting list of user-readable texts.

  

  (string)

    

    

  

