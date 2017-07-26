[ :ref:`aws <cli:aws>` . :ref:`clouddirectory <cli:aws clouddirectory>` ]

.. _cli:aws clouddirectory delete-typed-link-facet:


***********************
delete-typed-link-facet
***********************



===========
Description
===========



Deletes a  TypedLinkFacet . For more information, see `Typed link <http://docs.aws.amazon.com/directoryservice/latest/admin-guide/objectsandlinks.html#typedlink>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/clouddirectory-2016-05-10/DeleteTypedLinkFacet>`_


========
Synopsis
========

::

    delete-typed-link-facet
  --schema-arn <value>
  --name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--schema-arn`` (string)


  The Amazon Resource Name (ARN) that is associated with the schema. For more information, see  arns .

  

``--name`` (string)


  The unique name of the typed link facet.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

