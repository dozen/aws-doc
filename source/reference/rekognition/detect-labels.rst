[ :ref:`aws <cli:aws>` . :ref:`rekognition <cli:aws rekognition>` ]

.. _cli:aws rekognition detect-labels:


*************
detect-labels
*************



===========
Description
===========



Detects instances of real-world labels within an image (JPEG or PNG) provided as input. This includes objects like flower, tree, and table; events like wedding, graduation, and birthday party; and concepts like landscape, evening, and nature. For an example, see  get-started-exercise-detect-labels .

 

For each object, scene, and concept the API returns one or more labels. Each label provides the object name, and the level of confidence that the image contains the object. For example, suppose the input image has a lighthouse, the sea, and a rock. The response will include all three labels, one for each object. 

 

 ``{Name: lighthouse, Confidence: 98.4629}``  

 

 ``{Name: rock,Confidence: 79.2097}``  

 

 ``{Name: sea,Confidence: 75.061}``  

 

In the preceding example, the operation returns one label for each of the three objects. The operation can also return multiple labels for the same object in the image. For example, if the input image shows a flower (for example, a tulip), the operation might return the following three labels. 

 

 ``{Name: flower,Confidence: 99.0562}``  

 

 ``{Name: plant,Confidence: 99.0562}``  

 

 ``{Name: tulip,Confidence: 99.0562}``  

 

In this example, the detection algorithm more precisely identifies the flower as a tulip.

 

You can provide the input image as an S3 object or as base64-encoded bytes. In response, the API returns an array of labels. In addition, the response also includes the orientation correction. Optionally, you can specify ``MinConfidence`` to control the confidence threshold for the labels returned. The default is 50%. You can also add the ``MaxLabels`` parameter to limit the number of labels returned. 

 

.. note::

   

  If the object detected is a person, the operation doesn't provide the same facial details that the  detect-faces operation provides.

   

 

This is a stateless API operation. That is, the operation does not persist any data.

 

This operation requires permissions to perform the ``rekognition:DetectLabels`` action. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rekognition-2016-06-27/DetectLabels>`_


========
Synopsis
========

::

    detect-labels
  --image <value>
  [--max-labels <value>]
  [--min-confidence <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--image`` (structure)


  The input image. You can provide a blob of image bytes or an S3 object.

  



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



``--max-labels`` (integer)


  Maximum number of labels you want the service to return in the response. The service returns the specified number of highest confidence labels. 

  

``--min-confidence`` (float)


  Specifies the minimum confidence level for the labels to return. Amazon Rekognition doesn't return any labels with confidence lower than this specified value.

   

  If ``MinConfidence`` is not specified, the operation returns labels with a confidence values greater than or equal to 50 percent.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Labels -> (list)

  

  An array of labels for the real-world objects detected. 

  

  (structure)

    

    Structure containing details about the detected label, including name, and level of confidence.

    

    Name -> (string)

      

      The name (label) of the object.

      

      

    Confidence -> (float)

      

      Level of confidence.

      

      

    

  

OrientationCorrection -> (string)

  

  The orientation of the input image (counter-clockwise direction). If your application displays the image, you can use this value to correct the orientation. If Amazon Rekognition detects that the input image was rotated (for example, by 90 degrees), it first corrects the orientation before detecting the labels. 

   

  .. note::

     

    If the input image Exif metadata populates the orientation field, Amazon Rekognition does not perform orientation correction and the value of OrientationCorrection will be null.

     

  

  

