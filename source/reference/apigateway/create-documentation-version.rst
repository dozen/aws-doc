[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway create-documentation-version:


****************************
create-documentation-version
****************************



===========
Description
===========



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/CreateDocumentationVersion>`_


========
Synopsis
========

::

    create-documentation-version
  --rest-api-id <value>
  --documentation-version <value>
  [--stage-name <value>]
  [--description <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rest-api-id`` (string)


  [Required] The string identifier of the associated  RestApi .

  

``--documentation-version`` (string)


  [Required] The version identifier of the new snapshot.

  

``--stage-name`` (string)


  The stage name to be associated with the new documentation snapshot.

  

``--description`` (string)


  A description about the new documentation snapshot.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

version -> (string)

  

  The version identifier of the API documentation snapshot.

  

  

createdDate -> (timestamp)

  

  The date when the API documentation snapshot is created.

  

  

description -> (string)

  

  The description of the API documentation snapshot.

  

  

