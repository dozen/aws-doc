[ :ref:`aws <cli:aws>` . :ref:`rekognition <cli:aws rekognition>` ]

.. _cli:aws rekognition index-faces:


***********
index-faces
***********



===========
Description
===========



Detects faces in the input image and adds them to the specified collection. 

 

Amazon Rekognition does not save the actual faces detected. Instead, the underlying detection algorithm first detects the faces in the input image, and for each face extracts facial features into a feature vector, and stores it in the back-end database. Amazon Rekognition uses feature vectors when performing face match and search operations using the and operations. 

 

If you provide the optional ``externalImageID`` for the input image you provided, Amazon Rekognition associates this ID with all faces that it detects. When you call the operation, the response returns the external ID. You can use this external image ID to create a client-side index to associate the faces with each image. You can then use the index to find all faces in an image. 

 

In response, the operation returns an array of metadata for all detected faces. This includes, the bounding box of the detected face, confidence value (indicating the bounding box contains a face), a face ID assigned by the service for each face that is detected and stored, and an image ID assigned by the service for the input image. If you request all facial attributes (using the ``detectionAttributes`` parameter, Amazon Rekognition returns detailed facial attributes such as facial landmarks (for example, location of eye and mount) and other facial attributes such gender. If you provide the same image, specify the same collection, and use the same external ID in the ``index-faces`` operation, Amazon Rekognition doesn't save duplicate face metadata. 

 

For an example, see  example2 .

 

This operation requires permissions to perform the ``rekognition:IndexFaces`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rekognition-2016-06-27/IndexFaces>`_


========
Synopsis
========

::

    index-faces
  --collection-id <value>
  --image <value>
  [--external-image-id <value>]
  [--detection-attributes <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--collection-id`` (string)


  The ID of an existing collection to which you want to add the faces that are detected in the input images.

  

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



``--external-image-id`` (string)


  ID you want to assign to all the faces detected in the image.

  

``--detection-attributes`` (list)


  An array of facial attributes that you want to be returned. This can be the default list of attributes or all attributes. If you don't specify a value for ``detection-attributes`` or if you specify ``["DEFAULT"]`` , the API returns the following subset of facial attributes: ``BoundingBox`` , ``Confidence`` , ``Pose`` , ``Quality`` and ``Landmarks`` . If you provide ``["ALL"]`` , all facial attributes are returned but the operation will take longer to complete.

   

  If you provide both, ``["ALL", "DEFAULT"]`` , the service uses a logical AND operator to determine which attributes to return (in this case, all attributes). 

  



Syntax::

  "string" "string" ...

  Where valid values are:
    DEFAULT
    ALL





``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

FaceRecords -> (list)

  

  An array of faces detected and added to the collection. For more information, see  howitworks-index-faces . 

  

  (structure)

    

    Object containing both the face metadata (stored in the back-end database) and facial attributes that are detected but aren't stored in the database.

    

    Face -> (structure)

      

      Describes the face properties such as the bounding box, face ID, image ID of the input image, and external image ID that you assigned. 

      

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

        

        

      

    FaceDetail -> (structure)

      

      Structure containing attributes of the face that the algorithm detected.

      

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

          

          

        

      AgeRange -> (structure)

        

        The estimated age range, in years, for the face. Low represents the lowest estimated age and High represents the highest estimated age.

        

        Low -> (integer)

          

          The lowest estimated age.

          

          

        High -> (integer)

          

          The highest estimated age.

          

          

        

      Smile -> (structure)

        

        Indicates whether or not the face is smiling, and the confidence level in the determination.

        

        Value -> (boolean)

          

          Boolean value that indicates whether the face is smiling or not.

          

          

        Confidence -> (float)

          

          Level of confidence in the determination.

          

          

        

      Eyeglasses -> (structure)

        

        Indicates whether or not the face is wearing eye glasses, and the confidence level in the determination.

        

        Value -> (boolean)

          

          Boolean value that indicates whether the face is wearing eye glasses or not.

          

          

        Confidence -> (float)

          

          Level of confidence in the determination.

          

          

        

      Sunglasses -> (structure)

        

        Indicates whether or not the face is wearing sunglasses, and the confidence level in the determination.

        

        Value -> (boolean)

          

          Boolean value that indicates whether the face is wearing sunglasses or not.

          

          

        Confidence -> (float)

          

          Level of confidence in the determination.

          

          

        

      Gender -> (structure)

        

        Gender of the face and the confidence level in the determination.

        

        Value -> (string)

          

          Gender of the face.

          

          

        Confidence -> (float)

          

          Level of confidence in the determination.

          

          

        

      Beard -> (structure)

        

        Indicates whether or not the face has a beard, and the confidence level in the determination.

        

        Value -> (boolean)

          

          Boolean value that indicates whether the face has beard or not.

          

          

        Confidence -> (float)

          

          Level of confidence in the determination.

          

          

        

      Mustache -> (structure)

        

        Indicates whether or not the face has a mustache, and the confidence level in the determination.

        

        Value -> (boolean)

          

          Boolean value that indicates whether the face has mustache or not.

          

          

        Confidence -> (float)

          

          Level of confidence in the determination.

          

          

        

      EyesOpen -> (structure)

        

        Indicates whether or not the eyes on the face are open, and the confidence level in the determination.

        

        Value -> (boolean)

          

          Boolean value that indicates whether the eyes on the face are open.

          

          

        Confidence -> (float)

          

          Level of confidence in the determination.

          

          

        

      MouthOpen -> (structure)

        

        Indicates whether or not the mouth on the face is open, and the confidence level in the determination.

        

        Value -> (boolean)

          

          Boolean value that indicates whether the mouth on the face is open or not.

          

          

        Confidence -> (float)

          

          Level of confidence in the determination.

          

          

        

      Emotions -> (list)

        

        The emotions detected on the face, and the confidence level in the determination. For example, HAPPY, SAD, and ANGRY. 

        

        (structure)

          

          The emotions detected on the face, and the confidence level in the determination. For example, HAPPY, SAD, and ANGRY.

          

          Type -> (string)

            

            Type of emotion detected.

            

            

          Confidence -> (float)

            

            Level of confidence in the determination.

            

            

          

        

      Landmarks -> (list)

        

        Indicates the location of landmarks on the face.

        

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

        

        Identifies image brightness and sharpness.

        

        Brightness -> (float)

          

          Value representing brightness of the face. The service returns a value between 0 and 100 (inclusive). A higher value indicates a brighter face image.

          

          

        Sharpness -> (float)

          

          Value representing sharpness of the face. The service returns a value between 0 and 100 (inclusive). A higher value indicates a sharper face image.

          

          

        

      Confidence -> (float)

        

        Confidence level that the bounding box contains a face (and not a different object such as a tree).

        

        

      

    

  

OrientationCorrection -> (string)

  

  The orientation of the input image (counterclockwise direction). If your application displays the image, you can use this value to correct image orientation. The bounding box coordinates returned in ``FaceRecords`` represent face locations before the image orientation is corrected. 

   

  .. note::

     

    If the input image is in jpeg format, it might contain exchangeable image (Exif) metadata. If so, and the Exif metadata populates the orientation field, the value of ``OrientationCorrection`` is null and the bounding box coordinates in ``FaceRecords`` represent face locations after Exif metadata is used to correct the image orientation. Images in .png format don't contain Exif metadata.

     

  

  

