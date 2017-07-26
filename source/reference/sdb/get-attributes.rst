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



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sdb-2009-04-15/GetAttributes>`_


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
  [--generate-cli-skeleton <value>]




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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

      

      

      

      

    

  

