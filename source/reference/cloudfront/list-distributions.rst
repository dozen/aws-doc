[ :ref:`aws <cli:aws>` . :ref:`cloudfront <cli:aws cloudfront>` ]

.. _cli:aws cloudfront list-distributions:


******************
list-distributions
******************



===========
Description
===========

List distributions.

.. note::

  **AWS CLI support for this service is only available in a preview stage.** You can enable this service by running: ``aws configure set preview.cloudfront true`` 



``list-distributions`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``DistributionList.Items``


========
Synopsis
========

::

    list-distributions
  [--max-items <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--max-items`` (string)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--cli-input-json`` (string)
Performs service operation based on the JSON marker provided. The JSON marker follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (string)
 

  The size of each page.

   

  

  

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command retrieves a list of distributions::

  aws cloudfront list-distributions

Output::

  {
      "DistributionList": {
          "Marker": "",
          "Items": [
              {
                  "Status": "Deployed",
                  "CacheBehaviors": {
                      "Quantity": 0
                  },
                  "Origins": {
                      "Items": [
                          {
                              "OriginPath": "",
                              "S3OriginConfig": {
                                  "OriginAccessIdentity": ""
                              },
                              "Id": "my-origin",
                              "DomainName": "my-bucket.s3.amazonaws.com"
                          }
                      ],
                      "Quantity": 1
                  },
                  "DomainName": "d2wkuj2w9l34gt.cloudfront.net",
                  "PriceClass": "PriceClass_All",
                  "Enabled": true,
                  "DefaultCacheBehavior": {
                      "TrustedSigners": {
                          "Enabled": false,
                          "Quantity": 0
                      },
                      "TargetOriginId": "my-origin",
                      "ViewerProtocolPolicy": "allow-all",
                      "ForwardedValues": {
                          "Headers": {
                              "Quantity": 0
                          },
                          "Cookies": {
                              "Forward": "none"
                          },
                          "QueryString": true
                      },
                      "MaxTTL": 31536000,
                      "SmoothStreaming": false,
                      "DefaultTTL": 86400,
                      "AllowedMethods": {
                          "Items": [
                              "HEAD",
                              "GET"
                          ],
                          "CachedMethods": {
                              "Items": [
                                  "HEAD",
                                  "GET"
                              ],
                              "Quantity": 2
                          },
                          "Quantity": 2
                      },
                      "MinTTL": 3600
                  },
                  "Comment": "",
                  "ViewerCertificate": {
                      "CloudFrontDefaultCertificate": true,
                      "MinimumProtocolVersion": "SSLv3"
                  },
                  "CustomErrorResponses": {
                      "Quantity": 0
                  },
                  "LastModifiedTime": "2015-08-31T21:11:29.093Z",
                  "Id": "S11A16G5KZMEQD",
                  "Restrictions": {
                      "GeoRestriction": {
                          "RestrictionType": "none",
                          "Quantity": 0
                      }
                  },
                  "Aliases": {
                      "Quantity": 0
                  }
              }
          ],
          "IsTruncated": false,
          "MaxItems": 100,
          "Quantity": 1
      }
  }

======
Output
======

DistributionList -> (structure)

  The DistributionList type.

  Marker -> (string)

    The value you provided for the Marker request parameter.

    

  NextMarker -> (string)

    If IsTruncated is true, this element is present and contains the value you can use for the Marker request parameter to continue listing your distributions where they left off.

    

  MaxItems -> (integer)

    The value you provided for the MaxItems request parameter.

    

  IsTruncated -> (boolean)

    A flag that indicates whether more distributions remain to be listed. If your results were truncated, you can make a follow-up pagination request using the Marker request parameter to retrieve more distributions in the list.

    

  Quantity -> (integer)

    The number of distributions that were created by the current AWS account.

    

  Items -> (list)

    A complex type that contains one DistributionSummary element for each distribution that was created by the current AWS account.

    (structure)

      A summary of the information for an Amazon CloudFront distribution.

      Id -> (string)

        The identifier for the distribution. For example: EDFDVBD632BHDS5.

        

      Status -> (string)

        This response element indicates the current status of the distribution. When the status is Deployed, the distribution's information is fully propagated throughout the Amazon CloudFront system.

        

      LastModifiedTime -> (timestamp)

        The date and time the distribution was last modified.

        

      DomainName -> (string)

        The domain name corresponding to the distribution. For example: d604721fxaaqy9.cloudfront.net.

        

      Aliases -> (structure)

        A complex type that contains information about CNAMEs (alternate domain names), if any, for this distribution.

        Quantity -> (integer)

          The number of CNAMEs, if any, for this distribution.

          

        Items -> (list)

          Optional: A complex type that contains CNAME elements, if any, for this distribution. If Quantity is 0, you can omit Items.

          (string)

            

            

          

        

      Origins -> (structure)

        A complex type that contains information about origins for this distribution.

        Quantity -> (integer)

          The number of origins for this distribution.

          

        Items -> (list)

          A complex type that contains origins for this distribution.

          (structure)

            A complex type that describes the Amazon S3 bucket or the HTTP server (for example, a web server) from which CloudFront gets your files.You must create at least one origin.

            Id -> (string)

              A unique identifier for the origin. The value of Id must be unique within the distribution. You use the value of Id when you create a cache behavior. The Id identifies the origin that CloudFront routes a request to when the request matches the path pattern for that cache behavior.

              

            DomainName -> (string)

              Amazon S3 origins: The DNS name of the Amazon S3 bucket from which you want CloudFront to get objects for this origin, for example, myawsbucket.s3.amazonaws.com. Custom origins: The DNS domain name for the HTTP server from which you want CloudFront to get objects for this origin, for example, www.example.com.

              

            OriginPath -> (string)

              An optional element that causes CloudFront to request your content from a directory in your Amazon S3 bucket or your custom origin. When you include the OriginPath element, specify the directory name, beginning with a /. CloudFront appends the directory name to the value of DomainName.

              

            CustomHeaders -> (structure)

              A complex type that contains information about the custom headers associated with this Origin.

              Quantity -> (integer)

                The number of custom headers for this origin.

                

              Items -> (list)

                A complex type that contains the custom headers for this Origin.

                (structure)

                  A complex type that contains information related to a Header

                  HeaderName -> (string)

                    The header's name.

                    

                  HeaderValue -> (string)

                    The header's value.

                    

                  

                

              

            S3OriginConfig -> (structure)

              A complex type that contains information about the Amazon S3 origin. If the origin is a custom origin, use the CustomOriginConfig element instead.

              OriginAccessIdentity -> (string)

                The CloudFront origin access identity to associate with the origin. Use an origin access identity to configure the origin so that end users can only access objects in an Amazon S3 bucket through CloudFront. If you want end users to be able to access objects using either the CloudFront URL or the Amazon S3 URL, specify an empty OriginAccessIdentity element. To delete the origin access identity from an existing distribution, update the distribution configuration and include an empty OriginAccessIdentity element. To replace the origin access identity, update the distribution configuration and specify the new origin access identity. Use the format origin-access-identity/cloudfront/Id where Id is the value that CloudFront returned in the Id element when you created the origin access identity.

                

              

            CustomOriginConfig -> (structure)

              A complex type that contains information about a custom origin. If the origin is an Amazon S3 bucket, use the S3OriginConfig element instead.

              HTTPPort -> (integer)

                The HTTP port the custom origin listens on.

                

              HTTPSPort -> (integer)

                The HTTPS port the custom origin listens on.

                

              OriginProtocolPolicy -> (string)

                The origin protocol policy to apply to your origin.

                

              OriginSslProtocols -> (structure)

                The SSL/TLS protocols that you want CloudFront to use when communicating with your origin over HTTPS.

                Quantity -> (integer)

                  The number of SSL/TLS protocols that you want to allow CloudFront to use when establishing an HTTPS connection with this origin.

                  

                Items -> (list)

                  A complex type that contains one SslProtocol element for each SSL/TLS protocol that you want to allow CloudFront to use when establishing an HTTPS connection with this origin.

                  (string)

                    

                    

                  

                

              

            

          

        

      DefaultCacheBehavior -> (structure)

        A complex type that describes the default cache behavior if you do not specify a CacheBehavior element or if files don't match any of the values of PathPattern in CacheBehavior elements.You must create exactly one default cache behavior.

        TargetOriginId -> (string)

          The value of ID for the origin that you want CloudFront to route requests to when a request matches the path pattern either for a cache behavior or for the default cache behavior.

          

        ForwardedValues -> (structure)

          A complex type that specifies how CloudFront handles query strings, cookies and headers.

          QueryString -> (boolean)

            Indicates whether you want CloudFront to forward query strings to the origin that is associated with this cache behavior. If so, specify true; if not, specify false.

            

          Cookies -> (structure)

            A complex type that specifies how CloudFront handles cookies.

            Forward -> (string)

              Use this element to specify whether you want CloudFront to forward cookies to the origin that is associated with this cache behavior. You can specify all, none or whitelist. If you choose All, CloudFront forwards all cookies regardless of how many your application uses.

              

            WhitelistedNames -> (structure)

              A complex type that specifies the whitelisted cookies, if any, that you want CloudFront to forward to your origin that is associated with this cache behavior.

              Quantity -> (integer)

                The number of whitelisted cookies for this cache behavior.

                

              Items -> (list)

                Optional: A complex type that contains whitelisted cookies for this cache behavior. If Quantity is 0, you can omit Items.

                (string)

                  

                  

                

              

            

          Headers -> (structure)

            A complex type that specifies the Headers, if any, that you want CloudFront to vary upon for this cache behavior.

            Quantity -> (integer)

              The number of different headers that you want CloudFront to forward to the origin and to vary on for this cache behavior. The maximum number of headers that you can specify by name is 10. If you want CloudFront to forward all headers to the origin and vary on all of them, specify 1 for Quantity and * for Name. If you don't want CloudFront to forward any additional headers to the origin or to vary on any headers, specify 0 for Quantity and omit Items.

              

            Items -> (list)

              Optional: A complex type that contains a Name element for each header that you want CloudFront to forward to the origin and to vary on for this cache behavior. If Quantity is 0, omit Items.

              (string)

                

                

              

            

          

        TrustedSigners -> (structure)

          A complex type that specifies the AWS accounts, if any, that you want to allow to create signed URLs for private content. If you want to require signed URLs in requests for objects in the target origin that match the PathPattern for this cache behavior, specify true for Enabled, and specify the applicable values for Quantity and Items. For more information, go to Using a Signed URL to Serve Private Content in the Amazon CloudFront Developer Guide. If you don't want to require signed URLs in requests for objects that match PathPattern, specify false for Enabled and 0 for Quantity. Omit Items. To add, change, or remove one or more trusted signers, change Enabled to true (if it's currently false), change Quantity as applicable, and specify all of the trusted signers that you want to include in the updated distribution.

          Enabled -> (boolean)

            Specifies whether you want to require end users to use signed URLs to access the files specified by PathPattern and TargetOriginId.

            

          Quantity -> (integer)

            The number of trusted signers for this cache behavior.

            

          Items -> (list)

            Optional: A complex type that contains trusted signers for this cache behavior. If Quantity is 0, you can omit Items.

            (string)

              

              

            

          

        ViewerProtocolPolicy -> (string)

          Use this element to specify the protocol that users can use to access the files in the origin specified by TargetOriginId when a request matches the path pattern in PathPattern. If you want CloudFront to allow end users to use any available protocol, specify allow-all. If you want CloudFront to require HTTPS, specify https. If you want CloudFront to respond to an HTTP request with an HTTP status code of 301 (Moved Permanently) and the HTTPS URL, specify redirect-to-https. The viewer then resubmits the request using the HTTPS URL.

          

        MinTTL -> (long)

          The minimum amount of time that you want objects to stay in CloudFront caches before CloudFront queries your origin to see whether the object has been updated.You can specify a value from 0 to 3,153,600,000 seconds (100 years).

          

        AllowedMethods -> (structure)

          A complex type that controls which HTTP methods CloudFront processes and forwards to your Amazon S3 bucket or your custom origin. There are three choices: - CloudFront forwards only GET and HEAD requests. - CloudFront forwards only GET, HEAD and OPTIONS requests. - CloudFront forwards GET, HEAD, OPTIONS, PUT, PATCH, POST, and DELETE requests. If you pick the third choice, you may need to restrict access to your Amazon S3 bucket or to your custom origin so users can't perform operations that you don't want them to. For example, you may not want users to have permission to delete objects from your origin.

          Quantity -> (integer)

            The number of HTTP methods that you want CloudFront to forward to your origin. Valid values are 2 (for GET and HEAD requests), 3 (for GET, HEAD and OPTIONS requests) and 7 (for GET, HEAD, OPTIONS, PUT, PATCH, POST, and DELETE requests).

            

          Items -> (list)

            A complex type that contains the HTTP methods that you want CloudFront to process and forward to your origin.

            (string)

              

              

            

          CachedMethods -> (structure)

            A complex type that controls whether CloudFront caches the response to requests using the specified HTTP methods. There are two choices: - CloudFront caches responses to GET and HEAD requests. - CloudFront caches responses to GET, HEAD, and OPTIONS requests. If you pick the second choice for your S3 Origin, you may need to forward Access-Control-Request-Method, Access-Control-Request-Headers and Origin headers for the responses to be cached correctly.

            Quantity -> (integer)

              The number of HTTP methods for which you want CloudFront to cache responses. Valid values are 2 (for caching responses to GET and HEAD requests) and 3 (for caching responses to GET, HEAD, and OPTIONS requests).

              

            Items -> (list)

              A complex type that contains the HTTP methods that you want CloudFront to cache responses to.

              (string)

                

                

              

            

          

        SmoothStreaming -> (boolean)

          Indicates whether you want to distribute media files in Microsoft Smooth Streaming format using the origin that is associated with this cache behavior. If so, specify true; if not, specify false.

          

        DefaultTTL -> (long)

          If you don't configure your origin to add a Cache-Control max-age directive or an Expires header, DefaultTTL is the default amount of time (in seconds) that an object is in a CloudFront cache before CloudFront forwards another request to your origin to determine whether the object has been updated. The value that you specify applies only when your origin does not add HTTP headers such as Cache-Control max-age, Cache-Control s-maxage, and Expires to objects. You can specify a value from 0 to 3,153,600,000 seconds (100 years).

          

        MaxTTL -> (long)

          The maximum amount of time (in seconds) that an object is in a CloudFront cache before CloudFront forwards another request to your origin to determine whether the object has been updated. The value that you specify applies only when your origin adds HTTP headers such as Cache-Control max-age, Cache-Control s-maxage, and Expires to objects. You can specify a value from 0 to 3,153,600,000 seconds (100 years).

          

        Compress -> (boolean)

          Whether you want CloudFront to automatically compress content for web requests that include Accept-Encoding: gzip in the request header. If so, specify true; if not, specify false. CloudFront compresses files larger than 1000 bytes and less than 1 megabyte for both Amazon S3 and custom origins. When a CloudFront edge location is unusually busy, some files might not be compressed. The value of the Content-Type header must be on the list of file types that CloudFront will compress. For the current list, see `Serving Compressed Content`_ in the Amazon CloudFront Developer Guide. If you configure CloudFront to compress content, CloudFront removes the ETag response header from the objects that it compresses. The ETag header indicates that the version in a CloudFront edge cache is identical to the version on the origin server, but after compression the two versions are no longer identical. As a result, for compressed objects, CloudFront can't use the ETag header to determine whether an expired object in the CloudFront edge cache is still the latest version.

          

        

      CacheBehaviors -> (structure)

        A complex type that contains zero or more CacheBehavior elements.

        Quantity -> (integer)

          The number of cache behaviors for this distribution.

          

        Items -> (list)

          Optional: A complex type that contains cache behaviors for this distribution. If Quantity is 0, you can omit Items.

          (structure)

            A complex type that describes how CloudFront processes requests. You can create up to 10 cache behaviors.You must create at least as many cache behaviors (including the default cache behavior) as you have origins if you want CloudFront to distribute objects from all of the origins. Each cache behavior specifies the one origin from which you want CloudFront to get objects. If you have two origins and only the default cache behavior, the default cache behavior will cause CloudFront to get objects from one of the origins, but the other origin will never be used. If you don't want to specify any cache behaviors, include only an empty CacheBehaviors element. Don't include an empty CacheBehavior element, or CloudFront returns a MalformedXML error. To delete all cache behaviors in an existing distribution, update the distribution configuration and include only an empty CacheBehaviors element. To add, change, or remove one or more cache behaviors, update the distribution configuration and specify all of the cache behaviors that you want to include in the updated distribution.

            PathPattern -> (string)

              The pattern (for example, images/*.jpg) that specifies which requests you want this cache behavior to apply to. When CloudFront receives an end-user request, the requested path is compared with path patterns in the order in which cache behaviors are listed in the distribution. The path pattern for the default cache behavior is * and cannot be changed. If the request for an object does not match the path pattern for any cache behaviors, CloudFront applies the behavior in the default cache behavior.

              

            TargetOriginId -> (string)

              The value of ID for the origin that you want CloudFront to route requests to when a request matches the path pattern either for a cache behavior or for the default cache behavior.

              

            ForwardedValues -> (structure)

              A complex type that specifies how CloudFront handles query strings, cookies and headers.

              QueryString -> (boolean)

                Indicates whether you want CloudFront to forward query strings to the origin that is associated with this cache behavior. If so, specify true; if not, specify false.

                

              Cookies -> (structure)

                A complex type that specifies how CloudFront handles cookies.

                Forward -> (string)

                  Use this element to specify whether you want CloudFront to forward cookies to the origin that is associated with this cache behavior. You can specify all, none or whitelist. If you choose All, CloudFront forwards all cookies regardless of how many your application uses.

                  

                WhitelistedNames -> (structure)

                  A complex type that specifies the whitelisted cookies, if any, that you want CloudFront to forward to your origin that is associated with this cache behavior.

                  Quantity -> (integer)

                    The number of whitelisted cookies for this cache behavior.

                    

                  Items -> (list)

                    Optional: A complex type that contains whitelisted cookies for this cache behavior. If Quantity is 0, you can omit Items.

                    (string)

                      

                      

                    

                  

                

              Headers -> (structure)

                A complex type that specifies the Headers, if any, that you want CloudFront to vary upon for this cache behavior.

                Quantity -> (integer)

                  The number of different headers that you want CloudFront to forward to the origin and to vary on for this cache behavior. The maximum number of headers that you can specify by name is 10. If you want CloudFront to forward all headers to the origin and vary on all of them, specify 1 for Quantity and * for Name. If you don't want CloudFront to forward any additional headers to the origin or to vary on any headers, specify 0 for Quantity and omit Items.

                  

                Items -> (list)

                  Optional: A complex type that contains a Name element for each header that you want CloudFront to forward to the origin and to vary on for this cache behavior. If Quantity is 0, omit Items.

                  (string)

                    

                    

                  

                

              

            TrustedSigners -> (structure)

              A complex type that specifies the AWS accounts, if any, that you want to allow to create signed URLs for private content. If you want to require signed URLs in requests for objects in the target origin that match the PathPattern for this cache behavior, specify true for Enabled, and specify the applicable values for Quantity and Items. For more information, go to Using a Signed URL to Serve Private Content in the Amazon CloudFront Developer Guide. If you don't want to require signed URLs in requests for objects that match PathPattern, specify false for Enabled and 0 for Quantity. Omit Items. To add, change, or remove one or more trusted signers, change Enabled to true (if it's currently false), change Quantity as applicable, and specify all of the trusted signers that you want to include in the updated distribution.

              Enabled -> (boolean)

                Specifies whether you want to require end users to use signed URLs to access the files specified by PathPattern and TargetOriginId.

                

              Quantity -> (integer)

                The number of trusted signers for this cache behavior.

                

              Items -> (list)

                Optional: A complex type that contains trusted signers for this cache behavior. If Quantity is 0, you can omit Items.

                (string)

                  

                  

                

              

            ViewerProtocolPolicy -> (string)

              Use this element to specify the protocol that users can use to access the files in the origin specified by TargetOriginId when a request matches the path pattern in PathPattern. If you want CloudFront to allow end users to use any available protocol, specify allow-all. If you want CloudFront to require HTTPS, specify https. If you want CloudFront to respond to an HTTP request with an HTTP status code of 301 (Moved Permanently) and the HTTPS URL, specify redirect-to-https. The viewer then resubmits the request using the HTTPS URL.

              

            MinTTL -> (long)

              The minimum amount of time that you want objects to stay in CloudFront caches before CloudFront queries your origin to see whether the object has been updated.You can specify a value from 0 to 3,153,600,000 seconds (100 years).

              

            AllowedMethods -> (structure)

              A complex type that controls which HTTP methods CloudFront processes and forwards to your Amazon S3 bucket or your custom origin. There are three choices: - CloudFront forwards only GET and HEAD requests. - CloudFront forwards only GET, HEAD and OPTIONS requests. - CloudFront forwards GET, HEAD, OPTIONS, PUT, PATCH, POST, and DELETE requests. If you pick the third choice, you may need to restrict access to your Amazon S3 bucket or to your custom origin so users can't perform operations that you don't want them to. For example, you may not want users to have permission to delete objects from your origin.

              Quantity -> (integer)

                The number of HTTP methods that you want CloudFront to forward to your origin. Valid values are 2 (for GET and HEAD requests), 3 (for GET, HEAD and OPTIONS requests) and 7 (for GET, HEAD, OPTIONS, PUT, PATCH, POST, and DELETE requests).

                

              Items -> (list)

                A complex type that contains the HTTP methods that you want CloudFront to process and forward to your origin.

                (string)

                  

                  

                

              CachedMethods -> (structure)

                A complex type that controls whether CloudFront caches the response to requests using the specified HTTP methods. There are two choices: - CloudFront caches responses to GET and HEAD requests. - CloudFront caches responses to GET, HEAD, and OPTIONS requests. If you pick the second choice for your S3 Origin, you may need to forward Access-Control-Request-Method, Access-Control-Request-Headers and Origin headers for the responses to be cached correctly.

                Quantity -> (integer)

                  The number of HTTP methods for which you want CloudFront to cache responses. Valid values are 2 (for caching responses to GET and HEAD requests) and 3 (for caching responses to GET, HEAD, and OPTIONS requests).

                  

                Items -> (list)

                  A complex type that contains the HTTP methods that you want CloudFront to cache responses to.

                  (string)

                    

                    

                  

                

              

            SmoothStreaming -> (boolean)

              Indicates whether you want to distribute media files in Microsoft Smooth Streaming format using the origin that is associated with this cache behavior. If so, specify true; if not, specify false.

              

            DefaultTTL -> (long)

              If you don't configure your origin to add a Cache-Control max-age directive or an Expires header, DefaultTTL is the default amount of time (in seconds) that an object is in a CloudFront cache before CloudFront forwards another request to your origin to determine whether the object has been updated. The value that you specify applies only when your origin does not add HTTP headers such as Cache-Control max-age, Cache-Control s-maxage, and Expires to objects. You can specify a value from 0 to 3,153,600,000 seconds (100 years).

              

            MaxTTL -> (long)

              The maximum amount of time (in seconds) that an object is in a CloudFront cache before CloudFront forwards another request to your origin to determine whether the object has been updated. The value that you specify applies only when your origin adds HTTP headers such as Cache-Control max-age, Cache-Control s-maxage, and Expires to objects. You can specify a value from 0 to 3,153,600,000 seconds (100 years).

              

            Compress -> (boolean)

              Whether you want CloudFront to automatically compress content for web requests that include Accept-Encoding: gzip in the request header. If so, specify true; if not, specify false. CloudFront compresses files larger than 1000 bytes and less than 1 megabyte for both Amazon S3 and custom origins. When a CloudFront edge location is unusually busy, some files might not be compressed. The value of the Content-Type header must be on the list of file types that CloudFront will compress. For the current list, see `Serving Compressed Content`_ in the Amazon CloudFront Developer Guide. If you configure CloudFront to compress content, CloudFront removes the ETag response header from the objects that it compresses. The ETag header indicates that the version in a CloudFront edge cache is identical to the version on the origin server, but after compression the two versions are no longer identical. As a result, for compressed objects, CloudFront can't use the ETag header to determine whether an expired object in the CloudFront edge cache is still the latest version.

              

            

          

        

      CustomErrorResponses -> (structure)

        A complex type that contains zero or more CustomErrorResponses elements.

        Quantity -> (integer)

          The number of custom error responses for this distribution.

          

        Items -> (list)

          Optional: A complex type that contains custom error responses for this distribution. If Quantity is 0, you can omit Items.

          (structure)

            A complex type that describes how you'd prefer CloudFront to respond to requests that result in either a 4xx or 5xx response. You can control whether a custom error page should be displayed, what the desired response code should be for this error page and how long should the error response be cached by CloudFront. If you don't want to specify any custom error responses, include only an empty CustomErrorResponses element. To delete all custom error responses in an existing distribution, update the distribution configuration and include only an empty CustomErrorResponses element. To add, change, or remove one or more custom error responses, update the distribution configuration and specify all of the custom error responses that you want to include in the updated distribution.

            ErrorCode -> (integer)

              The 4xx or 5xx HTTP status code that you want to customize. For a list of HTTP status codes that you can customize, see CloudFront documentation.

              

            ResponsePagePath -> (string)

              The path of the custom error page (for example, /custom_404.html). The path is relative to the distribution and must begin with a slash (/). If the path includes any non-ASCII characters or unsafe characters as defined in RFC 1783 (http://www.ietf.org/rfc/rfc1738.txt), URL encode those characters. Do not URL encode any other characters in the path, or CloudFront will not return the custom error page to the viewer.

              

            ResponseCode -> (string)

              The HTTP status code that you want CloudFront to return with the custom error page to the viewer. For a list of HTTP status codes that you can replace, see CloudFront Documentation.

              

            ErrorCachingMinTTL -> (long)

              The minimum amount of time you want HTTP error codes to stay in CloudFront caches before CloudFront queries your origin to see whether the object has been updated. You can specify a value from 0 to 31,536,000.

              

            

          

        

      Comment -> (string)

        The comment originally specified when this distribution was created.

        

      PriceClass -> (string)

        

        

      Enabled -> (boolean)

        Whether the distribution is enabled to accept end user requests for content.

        

      ViewerCertificate -> (structure)

        A complex type that contains information about viewer certificates for this distribution.

        CloudFrontDefaultCertificate -> (boolean)

          If you want viewers to use HTTPS to request your objects and you're using the CloudFront domain name of your distribution in your object URLs (for example, https://d111111abcdef8.cloudfront.net/logo.jpg), set to true. Omit this value if you are setting an ACMCertificateArn or IAMCertificateId.

          

        IAMCertificateId -> (string)

          If you want viewers to use HTTPS to request your objects and you're using an alternate domain name in your object URLs (for example, https://example.com/logo.jpg), specify the IAM certificate identifier of the custom viewer certificate for this distribution. Specify either this value, ACMCertificateArn, or CloudFrontDefaultCertificate.

          

        ACMCertificateArn -> (string)

          If you want viewers to use HTTPS to request your objects and you're using an alternate domain name in your object URLs (for example, https://example.com/logo.jpg), specify the ACM certificate ARN of the custom viewer certificate for this distribution. Specify either this value, IAMCertificateId, or CloudFrontDefaultCertificate.

          

        SSLSupportMethod -> (string)

          If you specify a value for IAMCertificateId, you must also specify how you want CloudFront to serve HTTPS requests. Valid values are vip and sni-only. If you specify vip, CloudFront uses dedicated IP addresses for your content and can respond to HTTPS requests from any viewer. However, you must request permission to use this feature, and you incur additional monthly charges. If you specify sni-only, CloudFront can only respond to HTTPS requests from viewers that support Server Name Indication (SNI). All modern browsers support SNI, but some browsers still in use don't support SNI. Do not specify a value for SSLSupportMethod if you specified true for CloudFrontDefaultCertificate.

          

        MinimumProtocolVersion -> (string)

          Specify the minimum version of the SSL protocol that you want CloudFront to use, SSLv3 or TLSv1, for HTTPS connections. CloudFront will serve your objects only to browsers or devices that support at least the SSL version that you specify. The TLSv1 protocol is more secure, so we recommend that you specify SSLv3 only if your users are using browsers or devices that don't support TLSv1. If you're using a custom certificate (if you specify a value for IAMCertificateId) and if you're using dedicated IP (if you specify vip for SSLSupportMethod), you can choose SSLv3 or TLSv1 as the MinimumProtocolVersion. If you're using a custom certificate (if you specify a value for IAMCertificateId) and if you're using SNI (if you specify sni-only for SSLSupportMethod), you must specify TLSv1 for MinimumProtocolVersion.

          

        Certificate -> (string)

          Note: this field is deprecated. Please use one of [ACMCertificateArn, IAMCertificateId, CloudFrontDefaultCertificate].

          

        CertificateSource -> (string)

          Note: this field is deprecated. Please use one of [ACMCertificateArn, IAMCertificateId, CloudFrontDefaultCertificate].

          

        

      Restrictions -> (structure)

        A complex type that identifies ways in which you want to restrict distribution of your content.

        GeoRestriction -> (structure)

          A complex type that controls the countries in which your content is distributed. For more information about geo restriction, go to Customizing Error Responses in the Amazon CloudFront Developer Guide. CloudFront determines the location of your users using MaxMind GeoIP databases. For information about the accuracy of these databases, see How accurate are your GeoIP databases? on the MaxMind website.

          RestrictionType -> (string)

            The method that you want to use to restrict distribution of your content by country: - none: No geo restriction is enabled, meaning access to content is not restricted by client geo location. - blacklist: The Location elements specify the countries in which you do not want CloudFront to distribute your content. - whitelist: The Location elements specify the countries in which you want CloudFront to distribute your content.

            

          Quantity -> (integer)

            When geo restriction is enabled, this is the number of countries in your whitelist or blacklist. Otherwise, when it is not enabled, Quantity is 0, and you can omit Items.

            

          Items -> (list)

            A complex type that contains a Location element for each country in which you want CloudFront either to distribute your content (whitelist) or not distribute your content (blacklist). The Location element is a two-letter, uppercase country code for a country that you want to include in your blacklist or whitelist. Include one Location element for each country. CloudFront and MaxMind both use ISO 3166 country codes. For the current list of countries and the corresponding codes, see ISO 3166-1-alpha-2 code on the International Organization for Standardization website. You can also refer to the country list in the CloudFront console, which includes both country names and codes.

            (string)

              

              

            

          

        

      WebACLId -> (string)

        The Web ACL Id (if any) associated with the distribution.

        

      

    

  



.. _Serving Compressed Content: http://docs.aws.amazon.com/console/cloudfront/compressed-content
