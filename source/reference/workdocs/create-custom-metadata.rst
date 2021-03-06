[ :ref:`aws <cli:aws>` . :ref:`workdocs <cli:aws workdocs>` ]

.. _cli:aws workdocs create-custom-metadata:


**********************
create-custom-metadata
**********************



===========
Description
===========



Adds one or more custom properties to the specified resource (a folder, document, or version).



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/workdocs-2016-05-01/CreateCustomMetadata>`_


========
Synopsis
========

::

    create-custom-metadata
  [--authentication-token <value>]
  --resource-id <value>
  [--version-id <value>]
  --custom-metadata <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--authentication-token`` (string)


  Amazon WorkDocs authentication token. This field should not be set when using administrative API actions, as in accessing the API using AWS credentials.

  

``--resource-id`` (string)


  The ID of the resource.

  

``--version-id`` (string)


  The ID of the version, if the custom metadata is being added to a document version.

  

``--custom-metadata`` (map)


  Custom metadata in the form of name-value pairs.

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

