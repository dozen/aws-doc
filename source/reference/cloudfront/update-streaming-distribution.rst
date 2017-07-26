[ :ref:`aws <cli:aws>` . :ref:`cloudfront <cli:aws cloudfront>` ]

.. _cli:aws cloudfront update-streaming-distribution:


*****************************
update-streaming-distribution
*****************************



===========
Description
===========



Update a streaming distribution. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudfront-2017-03-25/UpdateStreamingDistribution>`_


.. note::

  **AWS CLI support for this service is only available in a preview stage.** You can enable this service by running: ``aws configure set preview.cloudfront true`` 



========
Synopsis
========

::

    update-streaming-distribution
  --streaming-distribution-config <value>
  --id <value>
  [--if-match <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--streaming-distribution-config`` (structure)


  The streaming distribution's configuration information.

  



Shorthand Syntax::

    CallerReference=string,S3Origin={DomainName=string,OriginAccessIdentity=string},Aliases={Quantity=integer,Items=[string,string]},Comment=string,Logging={Enabled=boolean,Bucket=string,Prefix=string},TrustedSigners={Enabled=boolean,Quantity=integer,Items=[string,string]},PriceClass=string,Enabled=boolean




JSON Syntax::

  {
    "CallerReference": "string",
    "S3Origin": {
      "DomainName": "string",
      "OriginAccessIdentity": "string"
    },
    "Aliases": {
      "Quantity": integer,
      "Items": ["string", ...]
    },
    "Comment": "string",
    "Logging": {
      "Enabled": true|false,
      "Bucket": "string",
      "Prefix": "string"
    },
    "TrustedSigners": {
      "Enabled": true|false,
      "Quantity": integer,
      "Items": ["string", ...]
    },
    "PriceClass": "PriceClass_100"|"PriceClass_200"|"PriceClass_All",
    "Enabled": true|false
  }



``--id`` (string)


  The streaming distribution's id.

  

``--if-match`` (string)


  The value of the ``ETag`` header that you received when retrieving the streaming distribution's configuration. For example: ``E2QWRUHAPOMQZL`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON id provided. The JSON id follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

StreamingDistribution -> (structure)

  

  The streaming distribution's information.

  

  Id -> (string)

    

    The identifier for the RTMP distribution. For example: ``EGTXBD79EXAMPLE`` .

    

    

  ARN -> (string)

    

    

  Status -> (string)

    

    The current status of the RTMP distribution. When the status is ``Deployed`` , the distribution's information is propagated to all CloudFront edge locations.

    

    

  LastModifiedTime -> (timestamp)

    

    The date and time that the distribution was last modified. 

    

    

  DomainName -> (string)

    

    The domain name that corresponds to the streaming distribution. For example: ``s5c39gqb8ow64r.cloudfront.net`` . 

    

    

  ActiveTrustedSigners -> (structure)

    

    A complex type that lists the AWS accounts, if any, that you included in the ``TrustedSigners`` complex type for this distribution. These are the accounts that you want to allow to create signed URLs for private content.

     

    The ``Signer`` complex type lists the AWS account number of the trusted signer or ``self`` if the signer is the AWS account that created the distribution. The ``Signer`` element also includes the IDs of any active CloudFront key pairs that are associated with the trusted signer's AWS account. If no ``KeyPairId`` element appears for a ``Signer`` , that signer can't create signed URLs.

     

    For more information, see `Serving Private Content through CloudFront <http://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/PrivateContent.html>`_ in the *Amazon CloudFront Developer Guide* . 

    

    Enabled -> (boolean)

      

      Enabled is ``true`` if any of the AWS accounts listed in the ``TrustedSigners`` complex type for this RTMP distribution have active CloudFront key pairs. If not, ``Enabled`` is ``false`` .

       

      For more information, see  ActiveTrustedSigners .

      

      

    Quantity -> (integer)

      

      A complex type that contains one ``Signer`` complex type for each trusted signer specified in the ``TrustedSigners`` complex type.

       

      For more information, see  ActiveTrustedSigners .

      

      

    Items -> (list)

      

      A complex type that contains one ``Signer`` complex type for each trusted signer that is specified in the ``TrustedSigners`` complex type.

       

      For more information, see  ActiveTrustedSigners . 

      

      (structure)

        

        A complex type that lists the AWS accounts that were included in the ``TrustedSigners`` complex type, as well as their active CloudFront key pair IDs, if any. 

        

        AwsAccountNumber -> (string)

          

          An AWS account that is included in the ``TrustedSigners`` complex type for this RTMP distribution. Valid values include:

           

           
          * ``self`` , which is the AWS account used to create the distribution. 
           
          * An AWS account number. 
           

          

          

        KeyPairIds -> (structure)

          

          A complex type that lists the active CloudFront key pairs, if any, that are associated with ``AwsAccountNumber`` .

          

          Quantity -> (integer)

            

            The number of active CloudFront key pairs for ``AwsAccountNumber`` .

             

            For more information, see  ActiveTrustedSigners .

            

            

          Items -> (list)

            

            A complex type that lists the active CloudFront key pairs, if any, that are associated with ``AwsAccountNumber`` .

             

            For more information, see  ActiveTrustedSigners .

            

            (string)

              

              

            

          

        

      

    

  StreamingDistributionConfig -> (structure)

    

    The current configuration information for the RTMP distribution.

    

    CallerReference -> (string)

      

      A unique number that ensures that the request can't be replayed. If the ``CallerReference`` is new (no matter the content of the ``streaming-distribution-config`` object), a new streaming distribution is created. If the ``CallerReference`` is a value that you already sent in a previous request to create a streaming distribution, and the content of the ``streaming-distribution-config`` is identical to the original request (ignoring white space), the response includes the same information returned to the original request. If the ``CallerReference`` is a value that you already sent in a previous request to create a streaming distribution but the content of the ``streaming-distribution-config`` is different from the original request, CloudFront returns a ``DistributionAlreadyExists`` error. 

      

      

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

          

          

        

      

    Comment -> (string)

      

      Any comments you want to include about the streaming distribution. 

      

      

    Logging -> (structure)

      

      A complex type that controls whether access logs are written for the streaming distribution. 

      

      Enabled -> (boolean)

        

        Specifies whether you want CloudFront to save access logs to an Amazon S3 bucket. If you do not want to enable logging when you create a streaming distribution or if you want to disable logging for an existing streaming distribution, specify ``false`` for ``Enabled`` , and specify ``empty Bucket`` and ``Prefix`` elements. If you specify ``false`` for ``Enabled`` but you specify values for ``Bucket`` and ``Prefix`` , the values are automatically deleted. 

        

        

      Bucket -> (string)

        

        The Amazon S3 bucket to store the access logs in, for example, ``myawslogbucket.s3.amazonaws.com`` .

        

        

      Prefix -> (string)

        

        An optional id that you want CloudFront to prefix to the access log ``filenames`` for this streaming distribution, for example, ``myprefix/`` . If you want to enable logging, but you do not want to specify a prefix, you still must include an empty ``Prefix`` element in the ``Logging`` element.

        

        

      

    TrustedSigners -> (structure)

      

      A complex type that specifies any AWS accounts that you want to permit to create signed URLs for private content. If you want the distribution to use signed URLs, include this element; if you want the distribution to use public URLs, remove this element. For more information, see `Serving Private Content through CloudFront <http://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/PrivateContent.html>`_ in the *Amazon CloudFront Developer Guide* . 

      

      Enabled -> (boolean)

        

        Specifies whether you want to require viewers to use signed URLs to access the files specified by ``PathPattern`` and ``TargetOriginId`` .

        

        

      Quantity -> (integer)

        

        The number of trusted signers for this cache behavior.

        

        

      Items -> (list)

        

         **Optional** : A complex type that contains trusted signers for this cache behavior. If ``Quantity`` is ``0`` , you can omit ``Items`` .

        

        (string)

          

          

        

      

    PriceClass -> (string)

      

      A complex type that contains information about price class for this streaming distribution. 

      

      

    Enabled -> (boolean)

      

      Whether the streaming distribution is enabled to accept user requests for content.

      

      

    

  

ETag -> (string)

  

  The current version of the configuration. For example: ``E2QWRUHAPOMQZL`` .

  

  

