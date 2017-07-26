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
 

 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sdb-2009-04-15/BatchDeleteAttributes>`_


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
  [--generate-cli-skeleton <value>]




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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None