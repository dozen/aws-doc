[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api delete-objects:


**************
delete-objects
**************



===========
Description
===========

This operation enables you to delete multiple objects from a bucket using a single HTTP request. You may specify up to 1000 keys.

========
Synopsis
========

::

    delete-objects
  --bucket <value>
  --delete <value>
  [--mfa <value>]
  [--request-payer <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--bucket`` (string)


``--delete`` (structure)




Shorthand Syntax::

    Objects=[{Key=string,VersionId=string},{Key=string,VersionId=string}],Quiet=boolean




JSON Syntax::

  {
    "Objects": [
      {
        "Key": "string",
        "VersionId": "string"
      }
      ...
    ],
    "Quiet": true|false
  }



``--mfa`` (string)
The concatenation of the authentication device's serial number, a space, and the value that is displayed on your authentication device.

``--request-payer`` (string)
Confirms that the requester knows that she or he will be charged for the request. Bucket owners need not specify this parameter in their requests. Documentation on downloading objects from requester pays buckets can be found at http://docs.aws.amazon.com/AmazonS3/latest/dev/ObjectsinRequesterPaysBuckets.html

  Possible values:

  
  *   ``requester``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command deletes an object from a bucket named ``my-bucket``::

  aws s3api delete-objects --bucket my-bucket --delete file://delete.json

``delete.json`` is a JSON document in the current directory that specifies the object to delete::

  {
    "Objects": [
      {
        "Key": "test1.txt"
      }
    ],
    "Quiet": false
  }

Output::

  {
      "Deleted": [
          {
              "DeleteMarkerVersionId": "mYAT5Mc6F7aeUL8SS7FAAqUPO1koHwzU",
              "Key": "test1.txt",
              "DeleteMarker": true
          }
      ]
  }

======
Output
======

Deleted -> (list)

  

  (structure)

    

    Key -> (string)

      

      

    VersionId -> (string)

      

      

    DeleteMarker -> (boolean)

      

      

    DeleteMarkerVersionId -> (string)

      

      

    

  

RequestCharged -> (string)

  If present, indicates that the requester was successfully charged for the request.

  

Errors -> (list)

  

  (structure)

    

    Key -> (string)

      

      

    VersionId -> (string)

      

      

    Code -> (string)

      

      

    Message -> (string)

      

      

    

  

