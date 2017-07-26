[ :ref:`aws <cli:aws>` . :ref:`cloudfront <cli:aws cloudfront>` ]

.. _cli:aws cloudfront get-streaming-distribution-config:


*********************************
get-streaming-distribution-config
*********************************



===========
Description
===========

Get the configuration information about a streaming distribution.

.. note::

  **AWS CLI support for this service is only available in a preview stage.** You can enable this service by running: ``aws configure set preview.cloudfront true`` 



========
Synopsis
========

::

    get-streaming-distribution-config
  --id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--id`` (string)
The streaming distribution's id.

``--cli-input-json`` (string)
Performs service operation based on the JSON id provided. The JSON id follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

StreamingDistributionConfig -> (structure)

  The streaming distribution's configuration information.

  CallerReference -> (string)

    A unique number that ensures the request can't be replayed. If the CallerReference is new (no matter the content of the StreamingDistributionConfig object), a new streaming distribution is created. If the CallerReference is a value you already sent in a previous request to create a streaming distribution, and the content of the StreamingDistributionConfig is identical to the original request (ignoring white space), the response includes the same information returned to the original request. If the CallerReference is a value you already sent in a previous request to create a streaming distribution but the content of the StreamingDistributionConfig is different from the original request, CloudFront returns a DistributionAlreadyExists error.

    

  S3Origin -> (structure)

    A complex type that contains information about the Amazon S3 bucket from which you want CloudFront to get your media files for distribution.

    DomainName -> (string)

      The DNS name of the S3 origin.

      

    OriginAccessIdentity -> (string)

      Your S3 origin's origin access identity.

      

    

  Aliases -> (structure)

    A complex type that contains information about CNAMEs (alternate domain names), if any, for this streaming distribution.

    Quantity -> (integer)

      The number of CNAMEs, if any, for this distribution.

      

    Items -> (list)

      Optional: A complex type that contains CNAME elements, if any, for this distribution. If Quantity is 0, you can omit Items.

      (string)

        

        

      

    

  Comment -> (string)

    Any comments you want to include about the streaming distribution.

    

  Logging -> (structure)

    A complex type that controls whether access logs are written for the streaming distribution.

    Enabled -> (boolean)

      Specifies whether you want CloudFront to save access logs to an Amazon S3 bucket. If you do not want to enable logging when you create a streaming distribution or if you want to disable logging for an existing streaming distribution, specify false for Enabled, and specify empty Bucket and Prefix elements. If you specify false for Enabled but you specify values for Bucket and Prefix, the values are automatically deleted.

      

    Bucket -> (string)

      The Amazon S3 bucket to store the access logs in, for example, myawslogbucket.s3.amazonaws.com.

      

    Prefix -> (string)

      An optional id that you want CloudFront to prefix to the access log filenames for this streaming distribution, for example, myprefix/. If you want to enable logging, but you do not want to specify a prefix, you still must include an empty Prefix element in the Logging element.

      

    

  TrustedSigners -> (structure)

    A complex type that specifies the AWS accounts, if any, that you want to allow to create signed URLs for private content. If you want to require signed URLs in requests for objects in the target origin that match the PathPattern for this cache behavior, specify true for Enabled, and specify the applicable values for Quantity and Items. For more information, go to Using a Signed URL to Serve Private Content in the Amazon CloudFront Developer Guide. If you don't want to require signed URLs in requests for objects that match PathPattern, specify false for Enabled and 0 for Quantity. Omit Items. To add, change, or remove one or more trusted signers, change Enabled to true (if it's currently false), change Quantity as applicable, and specify all of the trusted signers that you want to include in the updated distribution.

    Enabled -> (boolean)

      Specifies whether you want to require end users to use signed URLs to access the files specified by PathPattern and TargetOriginId.

      

    Quantity -> (integer)

      The number of trusted signers for this cache behavior.

      

    Items -> (list)

      Optional: A complex type that contains trusted signers for this cache behavior. If Quantity is 0, you can omit Items.

      (string)

        

        

      

    

  PriceClass -> (string)

    A complex type that contains information about price class for this streaming distribution.

    

  Enabled -> (boolean)

    Whether the streaming distribution is enabled to accept end user requests for content.

    

  

ETag -> (string)

  The current version of the configuration. For example: E2QWRUHAPOMQZL.

  

