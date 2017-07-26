[ :ref:`aws <cli:aws>` . :ref:`rekognition <cli:aws rekognition>` ]

.. _cli:aws rekognition compare-faces:


*************
compare-faces
*************



===========
Description
===========



Compares a face in the *source* input image with each face detected in the *target* input image. 

 

.. note::

   

  If the source image contains multiple faces, the service detects the largest face and compares it with each face detected in the target image. 

   

 

In response, the operation returns an array of face matches ordered by similarity score in descending order. For each face match, the response provides a bounding box of the face, facial landmarks, pose details (pitch, role, and yaw), quality (brightness and sharpness), and confidence value (indicating the level of confidence that the bounding box contains a face). The response also provides a similarity score, which indicates how closely the faces match. 

 

.. note::

   

  By default, only faces with a similarity score of greater than or equal to 80% are returned in the response. You can change this value by specifying the ``SimilarityThreshold`` parameter.

   

 

 ``compare-faces`` also returns an array of faces that don't match the source image. For each face, it returns a bounding box, confidence value, landmarks, pose details, and quality. The response also returns information about the face in the source image, including the bounding box of the face and confidence value.

 

If the image doesn't contain Exif metadata, ``compare-faces`` returns orientation information for the source and target images. Use these values to display the images with the correct image orientation.

 

.. note::

   

  This is a stateless API operation. That is, data returned by this operation doesn't persist.

   

 

For an example, see  get-started-exercise-compare-faces .

 

This operation requires permissions to perform the ``rekognition:CompareFaces`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rekognition-2016-06-27/CompareFaces>`_


========
Synopsis
========

::

    compare-faces
  --source-image <value>
  --target-image <value>
  [--similarity-threshold <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--source-image`` (structure)


  The source image, either as bytes or as an S3 object.

  



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



``--target-image`` (structure)


  The target image, either as bytes or as an S3 object.

  



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



``--similarity-threshold`` (float)


  The minimum level of confidence in the face matches that a match must meet to be included in the ``FaceMatches`` array.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

SourceImageFace -> (structure)

  

  The face in the source image that was used for comparison.

  

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

      

      

    

  Confidence -> (float)

    

    Confidence level that the selected bounding box contains a face.

    

    

  

FaceMatches -> (list)

  

  An array of faces in the target image that match the source image face. Each ``CompareFacesMatch`` object provides the bounding box, the confidence level that the bounding box contains a face, and the similarity score for the face in the bounding box and the face in the source image.

  

  (structure)

    

    Provides information about a face in a target image that matches the source image face analysed by ``compare-faces`` . The ``Face`` property contains the bounding box of the face in the target image. The ``Similarity`` property is the confidence that the source image face matches the face in the bounding box.

    

    Similarity -> (float)

      

      Level of confidence that the faces match.

      

      

    Face -> (structure)

      

      Provides face metadata (bounding box and confidence that the bounding box actually contains a face).

      

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

          

          

        

      Confidence -> (float)

        

        Level of confidence that what the bounding box contains is a face.

        

        

      Landmarks -> (list)

        

        An array of facial landmarks.

        

        (structure)

          

          Indicates the location of the landmark on the face.

          

          Type -> (string)

            

            Type of the landmark.

            

            

          X -> (float)

            

            x-coordinate from the top left of the landmark expressed as the ration of the width of the image. For example, if the images is 700x200 and the x-coordinate of the landmark is at 350 pixels, this value is 0.5. 

            

            

          Y -> (float)

            

            y-coordinate from the top left of the landmark expressed as the ration of the height of the image. For example, if the images is 700x200 and the y-coordinate of the landmark is at 100 pixels, this value is 0.5.

            

            

          

        

      Pose -> (structure)

        

        Indicates the pose of the face as determined by its pitch, roll, and yaw.

        

        Roll -> (float)

          

          Value representing the face rotation on the roll axis.

          

          

        Yaw -> (float)

          

          Value representing the face rotation on the yaw axis.

          

          

        Pitch -> (float)

          

          Value representing the face rotation on the pitch axis.

          

          

        

      Quality -> (structure)

        

        Identifies face image brightness and sharpness. 

        

        Brightness -> (float)

          

          Value representing brightness of the face. The service returns a value between 0 and 100 (inclusive). A higher value indicates a brighter face image.

          

          

        Sharpness -> (float)

          

          Value representing sharpness of the face. The service returns a value between 0 and 100 (inclusive). A higher value indicates a sharper face image.

          

          

        

      

    

  

UnmatchedFaces -> (list)

  

  An array of faces in the target image that did not match the source image face.

  

  (structure)

    

    Provides face metadata for target image faces that are analysed by ``compare-faces`` and ``recognize-celebrities`` .

    

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

        

        

      

    Confidence -> (float)

      

      Level of confidence that what the bounding box contains is a face.

      

      

    Landmarks -> (list)

      

      An array of facial landmarks.

      

      (structure)

        

        Indicates the location of the landmark on the face.

        

        Type -> (string)

          

          Type of the landmark.

          

          

        X -> (float)

          

          x-coordinate from the top left of the landmark expressed as the ration of the width of the image. For example, if the images is 700x200 and the x-coordinate of the landmark is at 350 pixels, this value is 0.5. 

          

          

        Y -> (float)

          

          y-coordinate from the top left of the landmark expressed as the ration of the height of the image. For example, if the images is 700x200 and the y-coordinate of the landmark is at 100 pixels, this value is 0.5.

          

          

        

      

    Pose -> (structure)

      

      Indicates the pose of the face as determined by its pitch, roll, and yaw.

      

      Roll -> (float)

        

        Value representing the face rotation on the roll axis.

        

        

      Yaw -> (float)

        

        Value representing the face rotation on the yaw axis.

        

        

      Pitch -> (float)

        

        Value representing the face rotation on the pitch axis.

        

        

      

    Quality -> (structure)

      

      Identifies face image brightness and sharpness. 

      

      Brightness -> (float)

        

        Value representing brightness of the face. The service returns a value between 0 and 100 (inclusive). A higher value indicates a brighter face image.

        

        

      Sharpness -> (float)

        

        Value representing sharpness of the face. The service returns a value between 0 and 100 (inclusive). A higher value indicates a sharper face image.

        

        

      

    

  

SourceImageOrientationCorrection -> (string)

  

  The orientation of the source image (counterclockwise direction). If your application displays the source image, you can use this value to correct image orientation. The bounding box coordinates returned in ``SourceImageFace`` represent the location of the face before the image orientation is corrected. 

   

  .. note::

     

    If the source image is in .jpeg format, it might contain exchangeable image (Exif) metadata that includes the image's orientation. If the Exif metadata for the source image populates the orientation field, the value of ``OrientationCorrection`` is null and the ``SourceImageFace`` bounding box coordinates represent the location of the face after Exif metadata is used to correct the orientation. Images in .png format don't contain Exif metadata.

     

  

  

TargetImageOrientationCorrection -> (string)

  

  The orientation of the target image (in counterclockwise direction). If your application displays the target image, you can use this value to correct the orientation of the image. The bounding box coordinates returned in ``FaceMatches`` and ``UnmatchedFaces`` represent face locations before the image orientation is corrected. 

   

  .. note::

     

    If the target image is in .jpg format, it might contain Exif metadata that includes the orientation of the image. If the Exif metadata for the target image populates the orientation field, the value of ``OrientationCorrection`` is null and the bounding box coordinates in ``FaceMatches`` and ``UnmatchedFaces`` represent the location of the face after Exif metadata is used to correct the orientation. Images in .png format don't contain Exif metadata.

     

  

  

