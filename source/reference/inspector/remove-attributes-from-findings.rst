[ :ref:`aws <cli:aws>` . :ref:`inspector <cli:aws inspector>` ]

.. _cli:aws inspector remove-attributes-from-findings:


*******************************
remove-attributes-from-findings
*******************************



===========
Description
===========



Removes the entire attribute (key and value pair) from the findings specified by the finding ARNs where an attribute with the specified key exists.



========
Synopsis
========

::

    remove-attributes-from-findings
  --finding-arns <value>
  --attribute-keys <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--finding-arns`` (list)


  The ARNs specifying the findings that you want to remove attributes from.

  



Syntax::

  "string" "string" ...



``--attribute-keys`` (list)


  The array of attribute keys that you want to remove from specified findings.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

message -> (string)

  

  Confirmation details of the action performed.

  

  

