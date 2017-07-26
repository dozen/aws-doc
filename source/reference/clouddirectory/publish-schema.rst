[ :ref:`aws <cli:aws>` . :ref:`clouddirectory <cli:aws clouddirectory>` ]

.. _cli:aws clouddirectory publish-schema:


**************
publish-schema
**************



===========
Description
===========



Publishes a development schema with a version. If description and attributes are specified, ``publish-schema`` overrides the development schema description and attributes. If not, the development schema description and attributes are used.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/clouddirectory-2016-05-10/PublishSchema>`_


========
Synopsis
========

::

    publish-schema
  --development-schema-arn <value>
  [--name <value>]
  --schema-version <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--development-schema-arn`` (string)


  The Amazon Resource Name (ARN) that is associated with the development schema. For more information, see  arns .

  

``--name`` (string)


  The new name under which the schema will be published. If this is not provided, the development schema is considered.

  

``--schema-version`` (string)


  The version under which the schema will be published.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

PublishedSchemaArn -> (string)

  

  The ARN that is associated with the published schema. For more information, see  arns .

  

  

