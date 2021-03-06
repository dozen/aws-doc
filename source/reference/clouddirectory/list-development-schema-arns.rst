[ :ref:`aws <cli:aws>` . :ref:`clouddirectory <cli:aws clouddirectory>` ]

.. _cli:aws clouddirectory list-development-schema-arns:


****************************
list-development-schema-arns
****************************



===========
Description
===========



Retrieves each Amazon Resource Name (ARN) of schemas in the development state.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/clouddirectory-2016-05-10/ListDevelopmentSchemaArns>`_


========
Synopsis
========

::

    list-development-schema-arns
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

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

SchemaArns -> (list)

  

  The ARNs of retrieved development schemas.

  

  (string)

    

    

  

NextToken -> (string)

  

  The pagination token.

  

  

