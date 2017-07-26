[ :ref:`aws <cli:aws>` . :ref:`clouddirectory <cli:aws clouddirectory>` ]

.. _cli:aws clouddirectory get-schema-as-json:


******************
get-schema-as-json
******************



===========
Description
===========



Retrieves a JSON representation of the schema. See `JSON Schema Format <http://docs.aws.amazon.com/directoryservice/latest/admin-guide/cd_schemas.html#jsonformat>`_ for more information.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/clouddirectory-2016-05-10/GetSchemaAsJson>`_


========
Synopsis
========

::

    get-schema-as-json
  --schema-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--schema-arn`` (string)


  The ARN of the schema to retrieve.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Name -> (string)

  

  The name of the retrieved schema.

  

  

Document -> (string)

  

  The JSON representation of the schema document.

  

  

