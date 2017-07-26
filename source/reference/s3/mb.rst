[ :ref:`aws <cli:aws>` . :ref:`s3 <cli:aws s3>` ]

.. _cli:aws s3 mb:


**
mb
**



===========
Description
===========

Creates an S3 bucket.



========
Synopsis
========

::

    mb
  <S3Uri>




=======
Options
=======

``paths`` (string)




========
Examples
========

The following ``mb`` command creates a bucket.  In this example, the user makes the bucket ``mybucket``.  The bucket is
created in the region specified in the user's configuration file::

    aws s3 mb s3://mybucket

Output::

    make_bucket: mybucket

The following ``mb`` command creates a bucket in a region specified by the ``--region`` parameter.  In this example, the
user makes the bucket ``mybucket`` in the region ``us-west-1``::

    aws s3 mb s3://mybucket --region us-west-1

Output::

    make_bucket: mybucket
