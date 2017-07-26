[ :ref:`aws <cli:aws>` . :ref:`rekognition <cli:aws rekognition>` ]

.. _cli:aws rekognition list-faces:


**********
list-faces
**********



===========
Description
===========



Returns metadata for faces in the specified collection. This metadata includes information such as the bounding box coordinates, the confidence (that the bounding box contains a face), and face ID. For an example, see  example3 . 

 

This operation requires permissions to perform the ``rekognition:ListFaces`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rekognition-2016-06-27/ListFaces>`_


``list-faces`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Faces``


========
Synopsis
========

::

    list-faces
  --collection-id <value>
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--collection-id`` (string)


  ID of the collection from which to list the faces.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Faces -> (list)

  

  An array of ``Face`` objects. 

  

  (structure)

    

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

      

      

    

  

NextToken -> (string)

  

  If the response is truncated, Amazon Rekognition returns this token that you can use in the subsequent request to retrieve the next set of faces.

  

  

