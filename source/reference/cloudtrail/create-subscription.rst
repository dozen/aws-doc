[ :ref:`aws <cli:aws>` . :ref:`cloudtrail <cli:aws cloudtrail>` ]

.. _cli:aws cloudtrail create-subscription:


*******************
create-subscription
*******************



===========
Description
===========

Creates and configures the AWS resources necessary to use CloudTrail, creates a trail using those resources, and turns on logging.



========
Synopsis
========

::

    aws cloudtrail create-subscription (--s3-use-bucket|--s3-new-bucket) bucket-name [--sns-new-topic topic-name]





=======
Options
=======

``--name`` (string)
Cloudtrail name

``--s3-new-bucket`` (string)
Create a new S3 bucket with this name

``--s3-use-bucket`` (string)
Use an existing S3 bucket with this name

``--s3-prefix`` (string)
S3 object prefix

``--sns-new-topic`` (string)
Create a new SNS topic with this name

``--include-global-service-events`` (string)
Whether to include global service events

``--s3-custom-policy`` (string)
Custom S3 policy template or URL

``--sns-custom-policy`` (string)
Custom SNS policy template or URL

