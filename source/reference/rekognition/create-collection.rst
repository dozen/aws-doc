[ :ref:`aws <cli:aws>` . :ref:`rekognition <cli:aws rekognition>` ]

.. _cli:aws rekognition create-collection:


*****************
create-collection
*****************



===========
Description
===========



Creates a collection in an AWS Region. You can add faces to the collection using the operation. 

 

For example, you might create collections, one for each of your application users. A user can then index faces using the ``index-faces`` operation and persist results in a specific collection. Then, a user can search the collection for faces in the user-specific container. 

 

.. note::

   

  Collection names are case-sensitive.

   

 

For an example, see  example1 . 

 

This operation requires permissions to perform the ``rekognition:CreateCollection`` action.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rekognition-2016-06-27/CreateCollection>`_


========
Synopsis
========

::

    create-collection
  --collection-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--collection-id`` (string)


  ID for the collection that you are creating.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

StatusCode -> (integer)

  

  HTTP status code indicating the result of the operation.

  

  

CollectionArn -> (string)

  

  Amazon Resource Name (ARN) of the collection. You can use this to manage permissions on your resources. 

  

  

