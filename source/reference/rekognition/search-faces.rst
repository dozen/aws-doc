[ :ref:`aws <cli:aws>` . :ref:`rekognition <cli:aws rekognition>` ]

.. _cli:aws rekognition search-faces:


************
search-faces
************



===========
Description
===========



For a given input face ID, searches for matching faces in the collection the face belongs to. You get a face ID when you add a face to the collection using the  index-faces operation. The operation compares the features of the input face with faces in the specified collection. 

 

.. note::

   

  You can also search faces without indexing faces by using the ``search-faces-by-image`` operation.

   

 

The operation response returns an array of faces that match, ordered by similarity score with the highest similarity first. More specifically, it is an array of metadata for each face match that is found. Along with the metadata, the response also includes a ``confidence`` value for each face match, indicating the confidence that the specific face matches the input face. 

 

For an example, see  example3 .

 

This operation requires permissions to perform the ``rekognition:SearchFaces`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rekognition-2016-06-27/SearchFaces>`_


========
Synopsis
========

::

    search-faces
  --collection-id <value>
  --face-id <value>
  [--max-faces <value>]
  [--face-match-threshold <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--collection-id`` (string)


  ID of the collection the face belongs to.

  

``--face-id`` (string)


  ID of a face to find matches for in the collection.

  

``--max-faces`` (integer)


  Maximum number of faces to return. The operation returns the maximum number of faces with the highest confidence in the match.

  

``--face-match-threshold`` (float)


  Optional value specifying the minimum confidence in the face match to return. For example, don't return any matches where confidence in matches is less than 70%.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

SearchedFaceId -> (string)

  

  ID of the face that was searched for matches in a collection.

  

  

FaceMatches -> (list)

  

  An array of faces that matched the input face, along with the confidence in the match.

  

  (structure)

    

    Provides face metadata. In addition, it also provides the confidence in the match of this face with the input face.

    

    Similarity -> (float)

      

      Confidence in the match of this face with the input face.

      

      

    Face -> (structure)

      

      Describes the face properties such as the bounding box, face ID, image ID of the source image, and external image ID that you assigned.

      

      FaceId -> (string)

        

        Unique identifier that Amazon Rekognition assigns to the face.

        

        

      BoundingBox -> (structure)

        

        Bounding box of the face.

        

        Width -> (float)

          

          Width of the bounding box as a ratio of the overall image width.

          

          

        Height -> (float)

          

          Height of the bounding box as a ratio of the overall image height.

          

          

        Left -> (float)

          

          Left coordinate of the bounding box as a ratio of overall image width.

          

          

        Top -> (float)

          

          Top coordinate of the bounding box as a ratio of overall image height.

          

          

        

      ImageId -> (string)

        

        Unique identifier that Amazon Rekognition assigns to the input image.

        

        

      ExternalImageId -> (string)

        

        Identifier that you assign to all the faces in the input image.

        

        

      Confidence -> (float)

        

        Confidence level that the bounding box contains a face (and not a different object such as a tree).

        

        

      

    

  

