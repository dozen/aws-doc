[ :ref:`aws <cli:aws>` . :ref:`ds <cli:aws ds>` ]

.. _cli:aws ds start-schema-extension:


**********************
start-schema-extension
**********************



===========
Description
===========



Applies a schema extension to a Microsoft AD directory.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ds-2015-04-16/StartSchemaExtension>`_


========
Synopsis
========

::

    start-schema-extension
  --directory-id <value>
  --create-snapshot-before-schema-extension | --no-create-snapshot-before-schema-extension
  --ldif-content <value>
  --description <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--directory-id`` (string)


  The identifier of the directory for which the schema extension will be applied to.

  

``--create-snapshot-before-schema-extension`` | ``--no-create-snapshot-before-schema-extension`` (boolean)


  If true, creates a snapshot of the directory before applying the schema extension.

  

``--ldif-content`` (string)


  The LDIF file represented as a string. To construct the ldif-content string, precede each line as it would be formatted in an ldif file with \n. See the example request below for more details. The file size can be no larger than 1MB.

  

``--description`` (string)


  A description of the schema extension.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

SchemaExtensionId -> (string)

  

  The identifier of the schema extension that will be applied.

  

  

