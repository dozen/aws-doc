[ :ref:`aws <cli:aws>` . :ref:`s3 <cli:aws s3>` ]

.. _cli:aws s3 website:


*******
website
*******



===========
Description
===========

Set the website configuration for a bucket.



========
Synopsis
========

::

    website
  <S3Uri>
  [--index-document <value>]
  [--error-document <value>]




=======
Options
=======

``paths`` (string)


``--index-document`` (string)
A suffix that is appended to a request that is for a directory on the website endpoint (e.g. if the suffix is index.html and you make a request to samplebucket/images/ the data that is returned will be for the object with the key name images/index.html) The suffix must not be empty and must not include a slash character.

``--error-document`` (string)
The object key name to use when a 4XX class error occurs.



========
Examples
========

The following command configures a bucket named ``my-bucket`` as a static website::

  aws s3 website s3://my-bucket/ --index-document index.html --error-document error.html

The index document option specifies the file in ``my-bucket`` that visitors will be directed to when they navigate to the website URL. In this case, the bucket is in the us-west-2 region, so the site would appear at ``http://my-bucket.s3-website-us-west-2.amazonaws.com``. 

All files in the bucket that appear on the static site must be configured to allow visitors to open them. File permissions are configured separately from the bucket website configuration. For information on hosting a static website in Amazon S3, see `Hosting a Static Website`_ in the *Amazon Simple Storage Service Developer Guide*.

.. _`Hosting a Static Website`: http://docs.aws.amazon.com/AmazonS3/latest/dev/WebsiteHosting.html