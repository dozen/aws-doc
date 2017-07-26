[ :ref:`aws <cli:aws>` ]

.. _cli:aws cloudtrail:


**********
cloudtrail
**********



===========
Description
===========

 

This is the CloudTrail API Reference. It provides descriptions of actions, data types, common parameters, and common errors for CloudTrail.

 

CloudTrail is a web service that records AWS API calls for your AWS account and delivers log files to an Amazon S3 bucket. The recorded information includes the identity of the user, the start time of the AWS API call, the source IP address, the request parameters, and the response elements returned by the service.

 

.. note::

  As an alternative to using the API, you can use one of the AWS SDKs, which consist of libraries and sample code for various programming languages and platforms (Java, Ruby, .NET, iOS, Android, etc.). The SDKs provide a convenient way to create programmatic access to AWSCloudTrail. For example, the SDKs take care of cryptographically signing requests, managing errors, and retrying requests automatically. For information about the AWS SDKs, including how to download and install them, see the `Tools for Amazon Web Services page`_ . 

 

See the CloudTrail User Guide for information about the data that is included with each AWS API call listed in the log files.



==================
Available Commands
==================


.. toctree::
  :maxdepth: 1
  :titlesonly:

  add-tags
  create-subscription
  create-trail
  delete-trail
  describe-trails
  get-trail-status
  list-public-keys
  list-tags
  lookup-events
  remove-tags
  start-logging
  stop-logging
  update-subscription
  update-trail
  validate-logs


.. _Tools for Amazon Web Services page: http://aws.amazon.com/tools/
