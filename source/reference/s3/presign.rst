[ :ref:`aws <cli:aws>` . :ref:`s3 <cli:aws s3>` ]

.. _cli:aws s3 presign:


*******
presign
*******



===========
Description
===========

Generate a pre-signed URL for an Amazon S3 object. This allows anyone who receives the pre-signed URL to retrieve the S3 object with an HTTP GET request. For sigv4 requests the region needs to be configured explicitly.



========
Synopsis
========

::

    presign
  <S3Uri>
  [--expires-in <value>]




=======
Options
=======

``path`` (string)


``--expires-in`` (integer)
Number of seconds until the pre-signed URL expires. Default is 3600 seconds.

