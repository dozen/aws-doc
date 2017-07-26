[ :ref:`aws <cli:aws>` . :ref:`clouddirectory <cli:aws clouddirectory>` ]

.. _cli:aws clouddirectory apply-schema:


************
apply-schema
************



===========
Description
===========



Copies the input published schema into the  Directory with the same name and version as that of the published schema .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/clouddirectory-2016-05-10/ApplySchema>`_


========
Synopsis
========

::

    apply-schema
  --published-schema-arn <value>
  --directory-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--published-schema-arn`` (string)


  Published schema Amazon Resource Name (ARN) that needs to be copied. For more information, see  arns .

  

``--directory-arn`` (string)


  The Amazon Resource Name (ARN) that is associated with the  Directory into which the schema is copied. For more information, see  arns .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

AppliedSchemaArn -> (string)

  

  The applied schema ARN that is associated with the copied schema in the  Directory . You can use this ARN to describe the schema information applied on this directory. For more information, see  arns .

  

  

DirectoryArn -> (string)

  

  The ARN that is associated with the  Directory . For more information, see  arns .

  

  

