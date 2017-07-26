[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector add-attributes-to-findings:


**************************
add-attributes-to-findings
**************************



===========
Description
===========



Assigns attributes (key and value pair) to the findings specified by the findings' ARNs.



========
Synopsis
========

::

    add-attributes-to-findings
  --finding-arns <value>
  --attributes <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--finding-arns`` (list)


  The ARNs specifying the findings that you want to assign attributes to.

  



Syntax::

  "string" "string" ...



``--attributes`` (list)


  The array of attributes that you want to assign to specified findings.

  



Shorthand Syntax::

    key=string,value=string ...




JSON Syntax::

  [
    {
      "key": "string",
      "value": "string"
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

message -> (string)

  

  Confirmation details of the action performed.

  

  

