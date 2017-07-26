[ :ref:`aws <cli:aws>` . :ref:`clouddirectory <cli:aws clouddirectory>` ]

.. _cli:aws clouddirectory list-facet-names:


****************
list-facet-names
****************



===========
Description
===========



Retrieves the names of facets that exist in a schema.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/clouddirectory-2016-05-10/ListFacetNames>`_


========
Synopsis
========

::

    list-facet-names
  --schema-arn <value>
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--schema-arn`` (string)


  The Amazon Resource Name (ARN) to retrieve facet names from.

  

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

  

  The names of facets that exist within the schema.

  

  (string)

    

    

  

NextToken -> (string)

  

  The pagination token.

  

  

