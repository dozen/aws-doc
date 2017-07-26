[ :ref:`aws <cli:aws>` . :ref:`cloudfront <cli:aws cloudfront>` ]

.. _cli:aws cloudfront list-streaming-distributions:


****************************
list-streaming-distributions
****************************



===========
Description
===========



List streaming distributions. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudfront-2017-03-25/ListStreamingDistributions>`_


.. note::

  **AWS CLI support for this service is only available in a preview stage.** You can enable this service by running: ``aws configure set preview.cloudfront true`` 



``list-streaming-distributions`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``StreamingDistributionList.Items``


========
Synopsis
========

::

    list-streaming-distributions
  [--max-items <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--max-items`` (string)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--cli-input-json`` (string)
Performs service operation based on the JSON marker provided. The JSON marker follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (string)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

StreamingDistributionList -> (structure)

  

  The ``StreamingDistributionList`` type. 

  

  Marker -> (string)

    

    The value you provided for the ``Marker`` request parameter. 

    

    

  NextMarker -> (string)

    

    If ``IsTruncated`` is ``true`` , this element is present and contains the value you can use for the ``Marker`` request parameter to continue listing your RTMP distributions where they left off. 

    

    

  MaxItems -> (integer)

    

    The value you provided for the ``MaxItems`` request parameter. 

    

    

  IsTruncated -> (boolean)

    

    A flag that indicates whether more streaming distributions remain to be listed. If your results were truncated, you can make a follow-up pagination request using the ``Marker`` request parameter to retrieve more distributions in the list. 

    

    

  Quantity -> (integer)

    

    The number of streaming distributions that were created by the current AWS account. 

    

    

  Items -> (list)

    

    A complex type that contains one ``StreamingDistributionSummary`` element for each distribution that was created by the current AWS account.

    

    (structure)

      

      A summary of the information for an Amazon CloudFront streaming distribution.

      

      Id -> (string)

        

        The identifier for the distribution. For example: ``EDFDVBD632BHDS5`` .

        

        

      ARN -> (string)

        

        The ARN (Amazon Resource Name) for the streaming distribution. For example: ``arn:aws:cloudfront::123456789012:streaming-distribution/EDFDVBD632BHDS5`` , where ``123456789012`` is your AWS account ID.

        

        

      Status -> (string)

        

        Indicates the current status of the distribution. When the status is ``Deployed`` , the distribution's information is fully propagated throughout the Amazon CloudFront system.

        

        

      LastModifiedTime -> (timestamp)

        

        The date and time the distribution was last modified.

        

        

      DomainName -> (string)

        

        The domain name corresponding to the distribution. For example: ``d604721fxaaqy9.cloudfront.net`` .

        

        

      S3Origin -> (structure)

        

        A complex type that contains information about the Amazon S3 bucket from which you want CloudFront to get your media files for distribution.

        

        DomainName -> (string)

          

          The DNS name of the Amazon S3 origin. 

          

          

        OriginAccessIdentity -> (string)

          

          The CloudFront origin access identity to associate with the RTMP distribution. Use an origin access identity to configure the distribution so that end users can only access objects in an Amazon S3 bucket through CloudFront.

           

          If you want end users to be able to access objects using either the CloudFront URL or the Amazon S3 URL, specify an empty ``OriginAccessIdentity`` element.

           

          To delete the origin access identity from an existing distribution, update the distribution configuration and include an empty ``OriginAccessIdentity`` element.

           

          To replace the origin access identity, update the distribution configuration and specify the new origin access identity.

           

          For more information, see `Using an Origin Access Identity to Restrict Access to Your Amazon S3 Content <http://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/private-content-restricting-access-to-s3.html>`_ in the *Amazon Amazon CloudFront Developer Guide* .

          

          

        

      Aliases -> (structure)

        

        A complex type that contains information about CNAMEs (alternate domain names), if any, for this streaming distribution.

        

        Quantity -> (integer)

          

          The number of CNAME aliases, if any, that you want to associate with this distribution.

          

          

        Items -> (list)

          

          A complex type that contains the CNAME aliases, if any, that you want to associate with this distribution.

          

          (string)

            

            

          

        

      TrustedSigners -> (structure)

        

        A complex type that specifies the AWS accounts, if any, that you want to allow to create signed URLs for private content. If you want to require signed URLs in requests for objects in the target origin that match the ``PathPattern`` for this cache behavior, specify ``true`` for ``Enabled`` , and specify the applicable values for ``Quantity`` and ``Items`` .If you don't want to require signed URLs in requests for objects that match ``PathPattern`` , specify ``false`` for ``Enabled`` and ``0`` for ``Quantity`` . Omit ``Items`` . To add, change, or remove one or more trusted signers, change ``Enabled`` to ``true`` (if it's currently ``false`` ), change ``Quantity`` as applicable, and specify all of the trusted signers that you want to include in the updated distribution.

        

        Enabled -> (boolean)

          

          Specifies whether you want to require viewers to use signed URLs to access the files specified by ``PathPattern`` and ``TargetOriginId`` .

          

          

        Quantity -> (integer)

          

          The number of trusted signers for this cache behavior.

          

          

        Items -> (list)

          

           **Optional** : A complex type that contains trusted signers for this cache behavior. If ``Quantity`` is ``0`` , you can omit ``Items`` .

          

          (string)

            

            

          

        

      Comment -> (string)

        

        The comment originally specified when this distribution was created.

        

        

      PriceClass -> (string)

        

        

      Enabled -> (boolean)

        

        Whether the distribution is enabled to accept end user requests for content.

        

        

      

    

  

