[ :ref:`aws <cli:aws>` . :ref:`events <cli:aws events>` ]

.. _cli:aws events list-targets-by-rule:


********************
list-targets-by-rule
********************



===========
Description
===========



Lists of targets assigned to the rule.



========
Synopsis
========

::

    list-targets-by-rule
  --rule <value>
  [--next-token <value>]
  [--limit <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--rule`` (string)


  The name of the rule whose targets you want to list.

  

``--next-token`` (string)


  The token returned by a previous call to indicate that there is more data available.

  

``--limit`` (integer)


  The maximum number of results to return.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Targets -> (list)

  

  Lists the targets assigned to the rule.

  

  (structure)

    

    Targets are the resources that can be invoked when a rule is triggered. For example, AWS Lambda functions, Amazon Kinesis streams, and built-in targets.

     

    **Input** and **InputPath** are mutually-exclusive and optional parameters of a target. When a rule is triggered due to a matched event, if for a target:

     

     
    * Neither **Input** nor **InputPath** is specified, then the entire event is passed to the target in JSON form.
     
    * **InputPath** is specified in the form of JSONPath (e.g. **$.detail** ), then only the part of the event specified in the path is passed to the target (e.g. only the detail part of the event is passed). 
     
    * **Input** is specified in the form of a valid JSON, then the matched event is overridden with this constant.
     

    

    Id -> (string)

      

      The unique target assignment ID.

      

      

    Arn -> (string)

      

      The Amazon Resource Name (ARN) associated of the target.

      

      

    Input -> (string)

      

      Valid JSON text passed to the target. For more information about JSON text, see `The JavaScript Object Notation (JSON) Data Interchange Format`_ .

      

      

    InputPath -> (string)

      

      The value of the JSONPath that is used for extracting part of the matched event when passing it to the target. For more information about JSON paths, see `JSONPath`_ .

      

      

    

  

NextToken -> (string)

  

  Indicates that there are additional results to retrieve.

  

  



.. _JSONPath: http://goessner.net/articles/JsonPath/
.. _The JavaScript Object Notation (JSON) Data Interchange Format: http://www.rfc-editor.org/rfc/rfc7159.txt
