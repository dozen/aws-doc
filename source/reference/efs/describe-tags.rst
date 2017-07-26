[ :ref:`aws <cli:aws>` . :ref:`efs <cli:aws efs>` ]

.. _cli:aws efs describe-tags:


*************
describe-tags
*************



===========
Description
===========



Returns the tags associated with a file system. The order of tags returned in the response of one ``describe-tags`` call, and the order of tags returned across the responses of a multi-call iteration (when using pagination), is unspecified. 

 

This operation requires permission for the ``elasticfilesystem:DescribeTags`` action. 



.. note::

  **AWS CLI support for this service is only available in a preview stage.** You can enable this service by running: ``aws configure set preview.efs true`` 



========
Synopsis
========

::

    describe-tags
  [--max-items <value>]
  [--marker <value>]
  --file-system-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--max-items`` (integer)


  Optional. Maximum number of file system tags to return in the response. It must be an integer with a value greater than zero.

  

``--marker`` (string)


  Optional. String. Opaque pagination token returned from a previous ``describe-tags`` operation. If present, it specifies to continue the list from where the previous call left off.

  

``--file-system-id`` (string)


  The ID of the file system whose tag set you want to retrieve.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Marker -> (string)

  

  If the request included a ``marker`` , the response returns that value in this field.

  

  

Tags -> (list)

  

  Returns tags associated with the file system as an array of ``Tag`` objects. 

  

  (structure)

    

    A tag is a pair of key and value. The allowed characters in keys and values are letters, whitespace, and numbers, representable in UTF-8, and the characters '+', '-', '=', '.', '_', ':', and '/'. 

    

    Key -> (string)

      

      Tag key, a string. The key must not start with "aws:".

      

      

    Value -> (string)

      

      Value of the tag key.

      

      

    

  

NextMarker -> (string)

  

  If a value is present, there are more tags to return. In a subsequent request, you can provide the value of ``NextMarker`` as the value of the ``marker`` parameter in your next request to retrieve the next set of tags.

  

  

