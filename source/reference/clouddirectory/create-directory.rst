[ :ref:`aws <cli:aws>` . :ref:`clouddirectory <cli:aws clouddirectory>` ]

.. _cli:aws clouddirectory create-directory:


****************
create-directory
****************



===========
Description
===========



Creates a  Directory by copying the published schema into the directory. A directory cannot be created without a schema.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/clouddirectory-2016-05-10/CreateDirectory>`_


========
Synopsis
========

::

    create-directory
  --name <value>
  --schema-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the  Directory . Should be unique per account, per region.

  

``--schema-arn`` (string)


  The Amazon Resource Name (ARN) of the published schema that will be copied into the data  Directory . For more information, see  arns .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DirectoryArn -> (string)

  

  The ARN that is associated with the  Directory . For more information, see  arns .

  

  

Name -> (string)

  

  The name of the  Directory .

  

  

ObjectIdentifier -> (string)

  

  The root object node of the created directory.

  

  

AppliedSchemaArn -> (string)

  

  The ARN of the published schema in the  Directory . Once a published schema is copied into the directory, it has its own ARN, which is referred to applied schema ARN. For more information, see  arns .

  

  

