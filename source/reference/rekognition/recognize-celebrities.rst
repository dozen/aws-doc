[ :ref:`aws <cli:aws>` . :ref:`rekognition <cli:aws rekognition>` ]

.. _cli:aws rekognition recognize-celebrities:


*********************
recognize-celebrities
*********************



===========
Description
===========



Returns an array of celebrities recognized in the input image. The image is passed either as base64-encoded image bytes or as a reference to an image in an Amazon S3 bucket. The image must be either a PNG or JPEG formatted file. For more information, see  celebrity-recognition . 

 

 ``recognize-celebrities`` returns the 15 largest faces in the image. It lists recognized celebrities in the ``CelebrityFaces`` list and unrecognized faces in the ``UnrecognizedFaces`` list. The operation doesn't return celebrities whose face sizes are smaller than the largest 15 faces in the image.

 

For each celebrity recognized, the API returns a ``Celebrity`` object. The ``Celebrity`` object contains the celebrity name, ID, URL links to additional information, match confidence, and a ``ComparedFace`` object that you can use to locate the celebrity's face on the image.

 

Rekognition does not retain information about which images a celebrity has been recognized in. Your application must store this information and use the ``Celebrity`` ID property as a unique identifier for the celebrity. If you don't store the celebrity name or additional information URLs returned by ``recognize-celebrities`` , you will need the ID to identify the celebrity in a call to the operation.

 

For an example, see  recognize-celebrities-tutorial .

 

This operation requires permissions to perform the ``rekognition:RecognizeCelebrities`` operation.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rekognition-2016-06-27/RecognizeCelebrities>`_


========
Synopsis
========

::

    recognize-celebrities
  --image <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--image`` (structure)


  The input image to use for celebrity recognition.

  



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



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

CelebrityFaces -> (list)

  

  Details about each celebrity found in the image. Amazon Rekognition can detect a maximum of 15 celebrities in an image.

  

  (structure)

    

    Provides information about a celebrity recognized by the operation.

    

    Urls -> (list)

      

      An array of URLs pointing to additional information about the celebrity. If there is no additional information about the celebrity, this list is empty.

      

      (string)

        

        

      

    Name -> (string)

      

      The name of the celebrity.

      

      

    Id -> (string)

      

      A unique identifier for the celebrity. 

      

      

    Face -> (structure)

      

      Provides information about the celebrity's face, such as its location on the image.

      

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

          

          

        

      

    MatchConfidence -> (float)

      

      The confidence, in percentage, that Rekognition has that the recognized face is the celebrity.

      

      

    

  

UnrecognizedFaces -> (list)

  

  Details about each unrecognized face in the image.

  

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

        

        

      

    

  

OrientationCorrection -> (string)

  

  The orientation of the input image (counterclockwise direction). If your application displays the image, you can use this value to correct the orientation. The bounding box coordinates returned in ``CelebrityFaces`` and ``UnrecognizedFaces`` represent face locations before the image orientation is corrected. 

   

  .. note::

     

    If the input image is in .jpeg format, it might contain exchangeable image (Exif) metadata that includes the image's orientation. If so, and the Exif metadata for the input image populates the orientation field, the value of ``OrientationCorrection`` is null and the ``CelebrityFaces`` and ``UnrecognizedFaces`` bounding box coordinates represent face locations after Exif metadata is used to correct the image orientation. Images in .png format don't contain Exif metadata. 

     

  

  

