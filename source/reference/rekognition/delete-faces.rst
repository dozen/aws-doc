[ :ref:`aws <cli:aws>` . :ref:`rekognition <cli:aws rekognition>` ]

.. _cli:aws rekognition delete-faces:


************
delete-faces
************



===========
Description
===========



Deletes faces from a collection. You specify a collection ID and an array of face IDs to remove from the collection.

 

This operation requires permissions to perform the ``rekognition:DeleteFaces`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rekognition-2016-06-27/DeleteFaces>`_


========
Synopsis
========

::

    delete-faces
  --collection-id <value>
  --face-ids <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--collection-id`` (string)


  Collection from which to remove the specific faces.

  

``--face-ids`` (list)


  An array of face IDs to delete.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DeletedFaces -> (list)

  

  An array of strings (face IDs) of the faces that were deleted.

  

  (string)

    

    

  

