[ :ref:`aws <cli:aws>` . :ref:`rekognition <cli:aws rekognition>` ]

.. _cli:aws rekognition detect-moderation-labels:


************************
detect-moderation-labels
************************



===========
Description
===========



Detects explicit or suggestive adult content in a specified JPEG or PNG format image. Use ``detect-moderation-labels`` to moderate images depending on your requirements. For example, you might want to filter images that contain nudity, but not images containing suggestive content.

 

To filter images, use the labels returned by ``detect-moderation-labels`` to determine which types of content are appropriate. For information about moderation labels, see  image-moderation .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rekognition-2016-06-27/DetectModerationLabels>`_


========
Synopsis
========

::

    detect-moderation-labels
  --image <value>
  [--min-confidence <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

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



``--min-confidence`` (float)


  Specifies the minimum confidence level for the labels to return. Amazon Rekognition doesn't return any labels with a confidence level lower than this specified value.

   

  If you don't specify ``MinConfidence`` , the operation returns labels with confidence values greater than or equal to 50 percent.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ModerationLabels -> (list)

  

  An array of labels for explicit or suggestive adult content found in the image. The list includes the top-level label and each child label detected in the image. This is useful for filtering specific categories of content. 

  

  (structure)

    

    Provides information about a single type of moderated content found in an image. Each type of moderated content has a label within a hierarchical taxonomy. For more information, see  image-moderation .

    

    Confidence -> (float)

      

      Specifies the confidence that Amazon Rekognition has that the label has been correctly identified.

       

      If you don't specify the ``MinConfidence`` parameter in the call to ``detect-moderation-labels`` , the operation returns labels with a confidence value greater than or equal to 50 percent.

      

      

    Name -> (string)

      

      The label name for the type of content detected in the image.

      

      

    ParentName -> (string)

      

      The name for the parent label. Labels at the top-level of the hierarchy have the parent label ``""`` .

      

      

    

  

