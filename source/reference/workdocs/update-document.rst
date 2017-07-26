[ :ref:`aws <cli:aws>` . :ref:`workdocs <cli:aws workdocs>` ]

.. _cli:aws workdocs update-document:


***************
update-document
***************



===========
Description
===========



Updates the specified attributes of a document. The user must have access to both the document and its parent folder, if applicable.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/workdocs-2016-05-01/UpdateDocument>`_


========
Synopsis
========

::

    update-document
  [--authentication-token <value>]
  --document-id <value>
  [--name <value>]
  [--parent-folder-id <value>]
  [--resource-state <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--authentication-token`` (string)


  Amazon WorkDocs authentication token. This field should not be set when using administrative API actions, as in accessing the API using AWS credentials.

  

``--document-id`` (string)


  The ID of the document.

  

``--name`` (string)


  The name of the document.

  

``--parent-folder-id`` (string)


  The ID of the parent folder.

  

``--resource-state`` (string)


  The resource state of the document. Note that only ACTIVE and RECYCLED are supported.

  

  Possible values:

  
  *   ``ACTIVE``

  
  *   ``RESTORING``

  
  *   ``RECYCLING``

  
  *   ``RECYCLED``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None