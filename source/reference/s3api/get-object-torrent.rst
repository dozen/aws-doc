[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api get-object-torrent:


******************
get-object-torrent
******************



===========
Description
===========

Return torrent files from a bucket.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/s3-2006-03-01/GetObjectTorrent>`_


========
Synopsis
========

::

    get-object-torrent
  --bucket <value>
  --key <value>
  [--request-payer <value>]
  outfile <value>




=======
Options
=======

``--bucket`` (string)


``--key`` (string)


``--request-payer`` (string)
Confirms that the requester knows that she or he will be charged for the request. Bucket owners need not specify this parameter in their requests. Documentation on downloading objects from requester pays buckets can be found at http://docs.aws.amazon.com/AmazonS3/latest/dev/ObjectsinRequesterPaysBuckets.html

  Possible values:

  
  *   ``requester``

  

  

``outfile`` (string)
Filename where the content will be saved



========
Examples
========

The following command creates a torrent for an object in a bucket named ``my-bucket``::

  aws s3api get-object-torrent --bucket my-bucket --key large-video-file.mp4 large-video-file.torrent

The torrent file is saved locally in the current folder. Note that the output filename (``large-video-file.torrent``) is specified without an option name and must be the last argument in the command.

======
Output
======

Body -> (blob)

  

  

RequestCharged -> (string)

  If present, indicates that the requester was successfully charged for the request.

  

