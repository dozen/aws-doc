[ :ref:`aws <cli:aws>` . :ref:`clouddirectory <cli:aws clouddirectory>` ]

.. _cli:aws clouddirectory list-typed-link-facet-names:


***************************
list-typed-link-facet-names
***************************



===========
Description
===========



Returns a paginated list of ``TypedLink`` facet names for a particular schema. For more information, see `Typed link <http://docs.aws.amazon.com/directoryservice/latest/admin-guide/objectsandlinks.html#typedlink>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/clouddirectory-2016-05-10/ListTypedLinkFacetNames>`_


========
Synopsis
========

::

    list-typed-link-facet-names
  --schema-arn <value>
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--schema-arn`` (string)


  The Amazon Resource Name (ARN) that is associated with the schema. For more information, see  arns .

  

``--next-token`` (string)


  The pagination token.

  

``--max-results`` (integer)


  The maximum number of results to retrieve.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

FacetNames -> (list)

  

  The names of typed link facets that exist within the schema.

  

  (string)

    

    

  

NextToken -> (string)

  

  The pagination token.

  

  

