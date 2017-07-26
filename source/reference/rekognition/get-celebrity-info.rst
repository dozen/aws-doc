[ :ref:`aws <cli:aws>` . :ref:`rekognition <cli:aws rekognition>` ]

.. _cli:aws rekognition get-celebrity-info:


******************
get-celebrity-info
******************



===========
Description
===========



Gets the name and additional information about a celebrity based on his or her Rekognition ID. The additional information is returned as an array of URLs. If there is no additional information about the celebrity, this list is empty. For more information, see  celebrity-recognition .

 

This operation requires permissions to perform the ``rekognition:GetCelebrityInfo`` action. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rekognition-2016-06-27/GetCelebrityInfo>`_


========
Synopsis
========

::

    get-celebrity-info
  --id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--id`` (string)


  The ID for the celebrity. You get the celebrity ID from a call to the operation, which recognizes celebrities in an image. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Urls -> (list)

  

  An array of URLs pointing to additional celebrity information. 

  

  (string)

    

    

  

Name -> (string)

  

  The name of the celebrity.

  

  

