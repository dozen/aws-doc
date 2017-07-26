[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway delete-file-share:


*****************
delete-file-share
*****************



===========
Description
===========



Deletes a file share from a file gateway. This operation is only supported in the file gateway architecture.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/storagegateway-2013-06-30/DeleteFileShare>`_


========
Synopsis
========

::

    delete-file-share
  --file-share-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--file-share-arn`` (string)


  The Amazon Resource Name (ARN) of the file share to be deleted. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

FileShareARN -> (string)

  

  The Amazon Resource Name (ARN) of the deleted file share. 

  

  

