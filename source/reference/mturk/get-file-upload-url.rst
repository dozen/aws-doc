[ :ref:`aws <cli:aws>` . :ref:`mturk <cli:aws mturk>` ]

.. _cli:aws mturk get-file-upload-url:


*******************
get-file-upload-url
*******************



===========
Description
===========



The ``get-file-upload-url`` operation generates and returns a temporary URL. You use the temporary URL to retrieve a file uploaded by a Worker as an answer to a FileUploadAnswer question for a HIT. The temporary URL is generated the instant the get-file-upload-url operation is called, and is valid for 60 seconds. You can get a temporary file upload URL any time until the HIT is disposed. After the HIT is disposed, any uploaded files are deleted, and cannot be retrieved. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/mturk-requester-2017-01-17/GetFileUploadURL>`_


========
Synopsis
========

::

    get-file-upload-url
  --assignment-id <value>
  --question-identifier <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--assignment-id`` (string)


  The ID of the assignment that contains the question with a FileUploadAnswer.

  

``--question-identifier`` (string)


  The identifier of the question with a FileUploadAnswer, as specified in the QuestionForm of the HIT.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

FileUploadURL -> (string)

  

  A temporary URL for the file that the Worker uploaded for the answer. 

  

  

