[ :ref:`aws <cli:aws>` . :ref:`sdb <cli:aws sdb>` ]

.. _cli:aws sdb get-attributes:


**************
get-attributes
**************



===========
Description
===========



Returns all of the attributes associated with the specified item. Optionally, the attributes returned can be limited to one or more attributes by specifying an attribute name parameter. 

 

If the item does not exist on the replica that was accessed for this operation, an empty set is returned. The system does not return an error as it cannot guarantee the item does not exist on other replicas. 



.. note::

  **AWS CLI support for this service is only available in a preview stage.** You can enable this service by running: ``aws configure set preview.sdb true`` 



========
Synopsis
========

::

    get-attributes
  --domain-name <value>
  --item-name <value>
  [--attribute-names <value>]
  [--consistent-read | --no-consistent-read]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain-name`` (string)
The name of the domain in which to perform the operation.

``--item-name`` (string)
The name of the item.

``--attribute-names`` (list)
The names of the attributes.



Syntax::

  "string" "string" ...



``--consistent-read`` | ``--no-consistent-read`` (boolean)
Determines whether or not strong consistency should be enforced when data is read from SimpleDB. If ``true`` , any data previously written to SimpleDB will be returned. Otherwise, results will be consistent eventually, and the client may not see data that was written immediately before your read.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Attributes -> (list)

  The list of attributes returned by the operation.

  (structure)

    

    

    

    Name -> (string)

      The name of the attribute.

      

    AlternateNameEncoding -> (string)

      

      

      

      

    Value -> (string)

      The value of the attribute.

      

    AlternateValueEncoding -> (string)

      

      

      

      

    

  

