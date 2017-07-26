[ :ref:`aws <cli:aws>` . :ref:`rekognition <cli:aws rekognition>` ]

.. _cli:aws rekognition search-faces-by-image:


*********************
search-faces-by-image
*********************



===========
Description
===========



For a given input image, first detects the largest face in the image, and then searches the specified collection for matching faces. The operation compares the features of the input face with faces in the specified collection. 

 

.. note::

   

  To search for all faces in an input image, you might first call the operation, and then use the face IDs returned in subsequent calls to the operation. 

   

  You can also call the ``detect-faces`` operation and use the bounding boxes in the response to make face crops, which then you can pass in to the ``search-faces-by-image`` operation. 

   

 

The response returns an array of faces that match, ordered by similarity score with the highest similarity first. More specifically, it is an array of metadata for each face match found. Along with the metadata, the response also includes a ``similarity`` indicating how similar the face is to the input face. In the response, the operation also returns the bounding box (and a confidence level that the bounding box contains a face) of the face that Amazon Rekognition used for the input image. 

 

For an example, see  example3 .

 

This operation requires permissions to perform the ``rekognition:SearchFacesByImage`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rekognition-2016-06-27/SearchFacesByImage>`_


========
Synopsis
========

::

    search-faces-by-image
  --collection-id <value>
  --image <value>
  [--max-faces <value>]
  [--face-match-threshold <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--collection-id`` (string)


  ID of the collection to search.

  

``--image`` (structure)


  The input image as bytes or an S3 object.

  



Shorthand Syntax::

    Bytes=blob,S3Object={Bucket=string,Name=string,Version=string}




JSON Syntax::

  {
    "Bytes": blob,
    "S3Object": {
      "Bucket": "string",
      "Name": "string",
      "Version": "string"
    }
  }



``--max-faces`` (integer)


  Maximum number of faces to return. The operation returns the maximum number of faces with the highest confidence in the match.

  

``--face-match-threshold`` (float)


  (Optional) Specifies the minimum confidence in the face match to return. For example, don't return any matches where confidence in matches is less than 70%.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

SearchedFaceBoundingBox -> (structure)

  

  The bounding box around the face in the input image that Amazon Rekognition used for the search.

  

  Width -> (float)

    

    Width of the bounding box as a ratio of the overall image width.

    

    

  Height -> (float)

    

    Height of the bounding box as a ratio of the overall image height.

    

    

  Left -> (float)

    

    Left coordinate of the bounding box as a ratio of overall image width.

    

    

  Top -> (float)

    

    Top coordinate of the bounding box as a ratio of overall image height.

    

    

  

SearchedFaceConfidence -> (float)

  

  The level of confidence that the ``searchedFaceBoundingBox`` , contains a face.

  

  

FaceMatches -> (list)

  

  An array of faces that match the input face, along with the confidence in the match.

  

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

        

        

      

    

  

