[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway get-documentation-versions:


**************************
get-documentation-versions
**************************



===========
Description
===========



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/GetDocumentationVersions>`_


========
Synopsis
========

::

    get-documentation-versions
  --rest-api-id <value>
  [--position <value>]
  [--limit <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rest-api-id`` (string)


  [Required] The string identifier of the associated  RestApi .

  

``--position`` (string)


  The current pagination position in the paged result set.

  

``--limit`` (integer)


  The maximum number of returned results per page.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

position -> (string)

  

  

items -> (list)

  

  The current page of elements from this collection.

  

  (structure)

    

    A snapshot of the documentation of an API.

     

    Publishing API documentation involves creating a documentation version associated with an API stage and exporting the versioned documentation to an external (e.g., Swagger) file.

      `Documenting an API <http://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-documenting-api.html>`_ ,  DocumentationPart ,  DocumentationVersions  

    version -> (string)

      

      The version identifier of the API documentation snapshot.

      

      

    createdDate -> (timestamp)

      

      The date when the API documentation snapshot is created.

      

      

    description -> (string)

      

      The description of the API documentation snapshot.

      

      

    

  

