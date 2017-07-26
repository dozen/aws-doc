[ :ref:`aws <cli:aws>` . :ref:`codecommit <cli:aws codecommit>` ]

.. _cli:aws codecommit get-blob:


********
get-blob
********



===========
Description
===========



Returns the base-64 encoded content of an individual blob within a repository.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/codecommit-2015-04-13/GetBlob>`_


========
Synopsis
========

::

    get-blob
  --repository-name <value>
  --blob-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--repository-name`` (string)


  The name of the repository that contains the blob.

  

``--blob-id`` (string)


  The ID of the blob, which is its SHA-1 pointer.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

content -> (blob)

  

  The content of the blob, usually a file.

  

  

