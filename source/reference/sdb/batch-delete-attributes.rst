[ :ref:`aws <cli:aws>` . :ref:`sdb <cli:aws sdb>` ]

.. _cli:aws sdb batch-delete-attributes:


***********************
batch-delete-attributes
***********************



===========
Description
===========



Performs multiple delete-attributes operations in a single call, which reduces round trips and latencies. This enables Amazon SimpleDB to optimize requests, which generally yields better throughput. 

 

The following limitations are enforced for this operation: 

 
* 1 MB request size
 
* 25 item limit per batch-delete-attributes operation
 

 



.. note::

  **AWS CLI support for this service is only available in a preview stage.** You can enable this service by running: ``aws configure set preview.sdb true`` 



========
Synopsis
========

::

    batch-delete-attributes
  --domain-name <value>
  --items <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain-name`` (string)
The name of the domain in which the attributes are being deleted.

``--items`` (list)
A list of items on which to perform the operation.



Shorthand Syntax::

    Name=string,Attributes=[{Name=string,AlternateNameEncoding=string,Value=string,AlternateValueEncoding=string},{Name=string,AlternateNameEncoding=string,Value=string,AlternateValueEncoding=string}] ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Attributes": [
        {
          "Name": "string",
          "AlternateNameEncoding": "string",
          "Value": "string",
          "AlternateValueEncoding": "string"
        }
        ...
      ]
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

None