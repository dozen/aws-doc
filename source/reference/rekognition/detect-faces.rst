[ :ref:`aws <cli:aws>` . :ref:`rekognition <cli:aws rekognition>` ]

.. _cli:aws rekognition detect-faces:


************
detect-faces
************



===========
Description
===========



Detects faces within an image (JPEG or PNG) that is provided as input.

 

For each face detected, the operation returns face details including a bounding box of the face, a confidence value (that the bounding box contains a face), and a fixed set of attributes such as facial landmarks (for example, coordinates of eye and mouth), gender, presence of beard, sunglasses, etc. 

 

The face-detection algorithm is most effective on frontal faces. For non-frontal or obscured faces, the algorithm may not detect the faces or might detect faces with lower confidence. 

 

.. note::

   

  This is a stateless API operation. That is, the operation does not persist any data.

   

 

For an example, see  get-started-exercise-detect-faces .

 

This operation requires permissions to perform the ``rekognition:DetectFaces`` action. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rekognition-2016-06-27/DetectFaces>`_


========
Synopsis
========

::

    detect-faces
  --image <value>
  [--attributes <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--image`` (structure)


  The image in which you want to detect faces. You can specify a blob or an S3 object. 

  



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



``--attributes`` (list)


  An array of facial attributes you want to be returned. This can be the default list of attributes or all attributes. If you don't specify a value for ``attributes`` or if you specify ``["DEFAULT"]`` , the API returns the following subset of facial attributes: ``BoundingBox`` , ``Confidence`` , ``Pose`` , ``Quality`` and ``Landmarks`` . If you provide ``["ALL"]`` , all facial attributes are returned but the operation will take longer to complete.

   

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

FaceDetails -> (list)

  

  Details of each face found in the image. 

  

  (structure)

    

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

  

  The orientation of the input image (counter-clockwise direction). If your application displays the image, you can use this value to correct image orientation. The bounding box coordinates returned in ``FaceDetails`` represent face locations before the image orientation is corrected. 

   

  .. note::

     

    If the input image is in .jpeg format, it might contain exchangeable image (Exif) metadata that includes the image's orientation. If so, and the Exif metadata for the input image populates the orientation field, the value of ``OrientationCorrection`` is null and the ``FaceDetails`` bounding box coordinates represent face locations after Exif metadata is used to correct the image orientation. Images in .png format don't contain Exif metadata.

     

  

  

