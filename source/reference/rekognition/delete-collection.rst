[ :ref:`aws <cli:aws>` . :ref:`rekognition <cli:aws rekognition>` ]

.. _cli:aws rekognition delete-collection:


*****************
delete-collection
*****************



===========
Description
===========



Deletes the specified collection. Note that this operation removes all faces in the collection. For an example, see  example1 .

 

This operation requires permissions to perform the ``rekognition:DeleteCollection`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rekognition-2016-06-27/DeleteCollection>`_


========
Synopsis
========

::

    delete-collection
  --collection-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--collection-id`` (string)


  ID of the collection to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

StatusCode -> (integer)

  

  HTTP status code that indicates the result of the operation.

  

  

