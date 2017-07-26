[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api delete-object:


*************
delete-object
*************



===========
Description
===========

Removes the null version (if there is one) of an object and inserts a delete marker, which becomes the latest version of the object. If there isn't a null version, Amazon S3 does not remove any objects.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/s3-2006-03-01/DeleteObject>`_


========
Synopsis
========

::

    delete-object
  --bucket <value>
  --key <value>
  [--mfa <value>]
  [--version-id <value>]
  [--request-payer <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--bucket`` (string)


``--key`` (string)


``--mfa`` (string)
The concatenation of the authentication device's serial number, a space, and the value that is displayed on your authentication device.

``--version-id`` (string)
VersionId used to reference a specific version of the object.

``--request-payer`` (string)
Confirms that the requester knows that she or he will be charged for the request. Bucket owners need not specify this parameter in their requests. Documentation on downloading objects from requester pays buckets can be found at http://docs.aws.amazon.com/AmazonS3/latest/dev/ObjectsinRequesterPaysBuckets.html

  Possible values:

  
  *   ``requester``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

The following command deletes an object named ``test.txt`` from a bucket named ``my-bucket``::

  aws s3api delete-object --bucket my-bucket --key test.txt

If bucket versioning is enabled, the output will contain the version ID of the delete marker::

  {
    "VersionId": "9_gKg5vG56F.TTEUdwkxGpJ3tNDlWlGq",
    "DeleteMarker": true
  }

For more information about deleting objects, see `Deleting Objects`_ in the *Amazon S3 Developer Guide*.

.. _`Deleting Objects`: http://docs.aws.amazon.com/AmazonS3/latest/dev/DeletingObjects.html


======
Output
======

DeleteMarker -> (boolean)

  Specifies whether the versioned object that was permanently deleted was (true) or was not (false) a delete marker.

  

VersionId -> (string)

  Returns the version ID of the delete marker created as a result of the DELETE operation.

  

RequestCharged -> (string)

  If present, indicates that the requester was successfully charged for the request.

  

