[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 list-change-batches-by-hosted-zone:


**********************************
list-change-batches-by-hosted-zone
**********************************



===========
Description
===========



This action gets the list of ChangeBatches in a given time period for a given hosted zone.



========
Synopsis
========

::

    list-change-batches-by-hosted-zone
  --hosted-zone-id <value>
  --start-date <value>
  --end-date <value>
  [--max-items <value>]
  [--marker <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--hosted-zone-id`` (string)


  The ID of the hosted zone that you want to see changes for.

  

``--start-date`` (string)


  The start of the time period you want to see changes for.

  

``--end-date`` (string)


  The end of the time period you want to see changes for.

  

``--max-items`` (string)


  The maximum number of items on a page.

  

``--marker`` (string)


  The page marker.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

MaxItems -> (string)

  

  The maximum number of items on a page.

  

  

Marker -> (string)

  

  The page marker.

  

  

IsTruncated -> (boolean)

  

  A flag that indicates if there are more change batches to list.

  

  

ChangeBatchRecords -> (list)

  

  The change batches within the given hosted zone and time period. 

  

  (structure)

    

    A complex type that lists the changes and information for a ChangeBatch.

    

    Id -> (string)

      

      The ID of the request. Use this ID to track when the change has completed across all Amazon Route 53 DNS servers.

      

      

    SubmittedAt -> (timestamp)

      

      The date and time the change was submitted, in the format ``YYYY-MM-DDThh:mm:ssZ`` , as specified in the ISO 8601 standard (for example, 2009-11-19T19:37:58Z). The ``Z`` after the time indicates that the time is listed in Coordinated Universal Time (UTC).

      

      

    Status -> (string)

      

      The current state of the request. ``PENDING`` indicates that this request has not yet been applied to all Amazon Route 53 DNS servers.

       

      Valid Values: ``PENDING`` | ``INSYNC`` 

      

      

    Comment -> (string)

      

      A complex type that describes change information about changes made to your hosted zone.

       

      This element contains an ID that you use when performing a  get-change action to get detailed information about the change.

      

      

    Submitter -> (string)

      

      The AWS account ID attached to the changes. 

      

      

    Changes -> (list)

      

      A list of changes made in the ChangeBatch.

      

      (structure)

        

        A complex type that contains the information for each change in a change batch request.

        

        Action -> (string)

          

          The action to perform:

           

           
          * ``CREATE`` : Creates a resource record set that has the specified values.
           
          * ``DELETE`` : Deletes a existing resource record set that has the specified values for ``Name`` , ``Type`` , ``SetIdentifier`` (for latency, weighted, geolocation, and failover resource record sets), and ``TTL`` (except alias resource record sets, for which the TTL is determined by the AWS resource that you're routing DNS queries to).
           
          * ``UPSERT`` : If a resource record set does not already exist, Amazon Route 53 creates it. If a resource record set does exist, Amazon Route 53 updates it with the values in the request. Amazon Route 53 can update an existing resource record set only when all of the following values match: ``Name`` , ``Type`` , and ``SetIdentifier`` (for weighted, latency, geolocation, and failover resource record sets).
           

          

          

        ResourceRecordSet -> (structure)

          

          Information about the resource record set to create or delete.

          

          Name -> (string)

            

            The name of the domain you want to perform the action on.

             

            Enter a fully qualified domain name, for example, ``www.example.com`` . You can optionally include a trailing dot. If you omit the trailing dot, Amazon Route 53 still assumes that the domain name that you specify is fully qualified. This means that Amazon Route 53 treats ``www.example.com`` (without a trailing dot) and ``www.example.com.`` (with a trailing dot) as identical.

             

            For information about how to specify characters other than a-z, 0-9, and - (hyphen) and how to specify internationalized domain names, see `DNS Domain Name Format`_ in the *Amazon Route 53 Developer Guide* .

             

            You can use an asterisk (*) character in the name. DNS treats the * character either as a wildcard or as the * character (ASCII 42), depending on where it appears in the name. For more information, see `Using an Asterisk (*) in the Names of Hosted Zones and Resource Record Sets`_ in the *Amazon Route 53 Developer Guide* 

             

            .. warning::

              You can't use the * wildcard for resource records sets that have a type of NS.

            

            

          Type -> (string)

            

            The DNS record type. For information about different record types and how data is encoded for them, see `Supported DNS Resource Record Types`_ in the *Amazon Route 53 Developer Guide* .

             

            Valid values for basic resource record sets: ``A`` | ``AAAA`` | ``CNAME`` | ``MX`` | ``NS`` | ``PTR`` | ``SOA`` | ``SPF`` | ``SRV`` | ``TXT`` 

             

            Values for weighted, latency, geolocation, and failover resource record sets: ``A`` | ``AAAA`` | ``CNAME`` | ``MX`` | ``PTR`` | ``SPF`` | ``SRV`` | ``TXT`` . When creating a group of weighted, latency, geolocation, or failover resource record sets, specify the same value for all of the resource record sets in the group.

             

            .. note::

              SPF records were formerly used to verify the identity of the sender of email messages. However, we no longer recommend that you create resource record sets for which the value of ``Type`` is ``SPF`` . RFC 7208, *Sender Policy Framework (SPF) for Authorizing Use of Domains in Email, Version 1* , has been updated to say, "...[I]ts existence and mechanism defined in [RFC4408] have led to some interoperability issues. Accordingly, its use is no longer appropriate for SPF version 1; implementations are not to use it." In RFC 7208, see section 14.1, `The SPF DNS Record Type`_ .

             

            Values for alias resource record sets:

             

             
            * **CloudFront distributions:**  ``A`` 
             
            * **ELB load balancers:**  ``A`` | ``AAAA`` 
             
            * **Amazon S3 buckets:** A
             
            * **Another resource record set in this hosted zone:** Specify the type of the resource record set for which you're creating the alias. Specify any value except ``NS`` or ``SOA`` .
             

            

            

          SetIdentifier -> (string)

            

            *Weighted, Latency, Geo, and Failover resource record sets only:* An identifier that differentiates among multiple resource record sets that have the same combination of DNS name and type. The value of ``SetIdentifier`` must be unique for each resource record set that has the same combination of DNS name and type.

            

            

          Weight -> (long)

            

            *Weighted resource record sets only:* Among resource record sets that have the same combination of DNS name and type, a value that determines the proportion of DNS queries that Amazon Route 53 responds to using the current resource record set. Amazon Route 53 calculates the sum of the weights for the resource record sets that have the same combination of DNS name and type. Amazon Route 53 then responds to queries based on the ratio of a resource's weight to the total. Note the following:

             

             
            * You must specify a value for the ``Weight`` element for every weighted resource record set.
             
            * You can only specify one ``ResourceRecord`` per weighted resource record set.
             
            * You cannot create latency, failover, or geolocation resource record sets that have the same values for the ``Name`` and ``Type`` elements as weighted resource record sets.
             
            * You can create a maximum of 100 weighted resource record sets that have the same values for the ``Name`` and ``Type`` elements.
             
            * For weighted (but not weighted alias) resource record sets, if you set ``Weight`` to ``0`` for a resource record set, Amazon Route 53 never responds to queries with the applicable value for that resource record set. However, if you set ``Weight`` to ``0`` for all resource record sets that have the same combination of DNS name and type, traffic is routed to all resources with equal probability. The effect of setting ``Weight`` to ``0`` is different when you associate health checks with weighted resource record sets. For more information, see `Options for Configuring Amazon Route 53 Active-Active and Active-Passive Failover`_ in the *Amazon Route 53 Developer Guide* . 
             

            

            

          Region -> (string)

            

            *Latency-based resource record sets only:* The Amazon EC2 region where the resource that is specified in this resource record set resides. The resource typically is an AWS resource, such as an Amazon EC2 instance or an ELB load balancer, and is referred to by an IP address or a DNS domain name, depending on the record type.

             

            .. note::

              You can create latency and latency alias resource record sets only in public hosted zones.

             

            When Amazon Route 53 receives a DNS query for a domain name and type for which you have created latency resource record sets, Amazon Route 53 selects the latency resource record set that has the lowest latency between the end user and the associated Amazon EC2 region. Amazon Route 53 then returns the value that is associated with the selected resource record set.

             

            Note the following:

             

             
            * You can only specify one ``ResourceRecord`` per latency resource record set.
             
            * You can only create one latency resource record set for each Amazon EC2 region.
             
            * You are not required to create latency resource record sets for all Amazon EC2 regions. Amazon Route 53 will choose the region with the best latency from among the regions for which you create latency resource record sets.
             
            * You cannot create non-latency resource record sets that have the same values for the ``Name`` and ``Type`` elements as latency resource record sets.
             

            

            

          GeoLocation -> (structure)

            

            *Geo location resource record sets only:* A complex type that lets you control how Amazon Route 53 responds to DNS queries based on the geographic origin of the query. For example, if you want all queries from Africa to be routed to a web server with an IP address of ``192.0.2.111`` , create a resource record set with a ``Type`` of ``A`` and a ``ContinentCode`` of ``AF`` .

             

            .. note::

              You can create geolocation and geolocation alias resource record sets only in public hosted zones.

             

            If you create separate resource record sets for overlapping geographic regions (for example, one resource record set for a continent and one for a country on the same continent), priority goes to the smallest geographic region. This allows you to route most queries for a continent to one resource and to route queries for a country on that continent to a different resource.

             

            You cannot create two geolocation resource record sets that specify the same geographic location.

             

            The value ``*`` in the ``CountryCode`` element matches all geographic locations that aren't specified in other geolocation resource record sets that have the same values for the ``Name`` and ``Type`` elements.

             

            .. warning::

              Geolocation works by mapping IP addresses to locations. However, some IP addresses aren't mapped to geographic locations, so even if you create geolocation resource record sets that cover all seven continents, Amazon Route 53 will receive some DNS queries from locations that it can't identify. We recommend that you create a resource record set for which the value of ``CountryCode`` is ``*`` , which handles both queries that come from locations for which you haven't created geolocation resource record sets and queries from IP addresses that aren't mapped to a location. If you don't create a ``*`` resource record set, Amazon Route 53 returns a "no answer" response for queries from those locations.

             

            You cannot create non-geolocation resource record sets that have the same values for the ``Name`` and ``Type`` elements as geolocation resource record sets.

            

            ContinentCode -> (string)

              

              The code for a continent geo location. Note: only continent locations have a continent code.

               

              Valid values: ``AF`` | ``AN`` | ``AS`` | ``EU`` | ``OC`` | ``NA`` | ``SA`` 

               

              Constraint: Specifying ``ContinentCode`` with either ``CountryCode`` or ``SubdivisionCode`` returns an  InvalidInput error.

              

              

            CountryCode -> (string)

              

              The code for a country geo location. The default location uses '*' for the country code and will match all locations that are not matched by a geo location.

               

              The default geo location uses a ``*`` for the country code. All other country codes follow the ISO 3166 two-character code.

              

              

            SubdivisionCode -> (string)

              

              The code for a country's subdivision (e.g., a province of Canada). A subdivision code is only valid with the appropriate country code.

               

              Constraint: Specifying ``SubdivisionCode`` without ``CountryCode`` returns an  InvalidInput error.

              

              

            

          Failover -> (string)

            

            *Failover resource record sets only:* To configure failover, you add the ``Failover`` element to two resource record sets. For one resource record set, you specify ``PRIMARY`` as the value for ``Failover`` ; for the other resource record set, you specify ``SECONDARY`` . In addition, you include the ``HealthCheckId`` element and specify the health check that you want Amazon Route 53 to perform for each resource record set.

             

            .. note::

              You can create failover and failover alias resource record sets only in public hosted zones.

             

            Except where noted, the following failover behaviors assume that you have included the ``HealthCheckId`` element in both resource record sets:

             

             
            * When the primary resource record set is healthy, Amazon Route 53 responds to DNS queries with the applicable value from the primary resource record set regardless of the health of the secondary resource record set.
             
            * When the primary resource record set is unhealthy and the secondary resource record set is healthy, Amazon Route 53 responds to DNS queries with the applicable value from the secondary resource record set.
             
            * When the secondary resource record set is unhealthy, Amazon Route 53 responds to DNS queries with the applicable value from the primary resource record set regardless of the health of the primary resource record set.
             
            * If you omit the ``HealthCheckId`` element for the secondary resource record set, and if the primary resource record set is unhealthy, Amazon Route 53 always responds to DNS queries with the applicable value from the secondary resource record set. This is true regardless of the health of the associated endpoint.
             

             

            You cannot create non-failover resource record sets that have the same values for the ``Name`` and ``Type`` elements as failover resource record sets.

             

            For failover alias resource record sets, you must also include the ``EvaluateTargetHealth`` element and set the value to true.

             

            For more information about configuring failover for Amazon Route 53, see `Amazon Route 53 Health Checks and DNS Failover`_ in the *Amazon Route 53 Developer Guide* .

             

            Valid values: ``PRIMARY`` | ``SECONDARY`` 

            

            

          TTL -> (long)

            

            The cache time to live for the current resource record set. Note the following:

             

             
            * If you're creating an alias resource record set, omit ``TTL`` . Amazon Route 53 uses the value of ``TTL`` for the alias target. 
             
            * If you're associating this resource record set with a health check (if you're adding a ``HealthCheckId`` element), we recommend that you specify a ``TTL`` of 60 seconds or less so clients respond quickly to changes in health status.
             
            * All of the resource record sets in a group of weighted, latency, geolocation, or failover resource record sets must have the same value for ``TTL`` .
             
            * If a group of weighted resource record sets includes one or more weighted alias resource record sets for which the alias target is an ELB load balancer, we recommend that you specify a ``TTL`` of 60 seconds for all of the non-alias weighted resource record sets that have the same name and type. Values other than 60 seconds (the TTL for load balancers) will change the effect of the values that you specify for ``Weight`` .
             

            

            

          ResourceRecords -> (list)

            

            A complex type that contains the resource records for the current resource record set.

            

            (structure)

              

              A complex type that contains the value of the ``Value`` element for the current resource record set.

              

              Value -> (string)

                

                The current or new DNS record value, not to exceed 4,000 characters. In the case of a ``DELETE`` action, if the current value does not match the actual value, an error is returned. For descriptions about how to format ``Value`` for different record types, see `Supported DNS Resource Record Types`_ in the *Amazon Route 53 Developer Guide* .

                 

                You can specify more than one value for all record types except ``CNAME`` and ``SOA`` . 

                

                

              

            

          AliasTarget -> (structure)

            

            *Alias resource record sets only:* Information about the AWS resource to which you are redirecting traffic.

            

            HostedZoneId -> (string)

              

              *Alias resource record sets only:* The value you use depends on where you want to route queries:

               

               
              * **A CloudFront distribution:** Specify ``Z2FDTNDATAQYW2`` .
               
              * An ELB load balancer: Specify the value of the hosted zone ID for the load balancer. You can get the hosted zone ID by using the AWS Management Console, the ELB API, or the AWS CLI. Use the same method to get values for ``HostedZoneId`` and ``DNSName`` . If you get one value from the console and the other value from the API or the CLI, creating the resource record set will fail.
               
              * **An Amazon S3 bucket that is configured as a static website:** Specify the hosted zone ID for the Amazon S3 website endpoint in which you created the bucket. For more information about valid values, see the table `Amazon Simple Storage Service (S3) Website Endpoints`_ in the *Amazon Web Services General Reference* .
               
              * **Another Amazon Route 53 resource record set in your hosted zone:** Specify the hosted zone ID of your hosted zone. (An alias resource record set cannot reference a resource record set in a different hosted zone.)
               

               

              For more information and an example, see `Example\: Creating Alias Resource Record Sets`_ in the *Amazon Route 53 API Reference* .

              

              

            DNSName -> (string)

              

              *Alias resource record sets only:* The external DNS name associated with the AWS Resource. The value that you specify depends on where you want to route queries:

               

               
              * **A CloudFront distribution:** Specify the domain name that CloudFront assigned when you created your distribution. Your CloudFront distribution must include an alternate domain name that matches the name of the resource record set. For example, if the name of the resource record set is ``acme.example.com`` , your CloudFront distribution must include ``acme.example.com`` as one of the alternate domain names. For more information, see `Using Alternate Domain Names (CNAMEs)`_ in the *Amazon CloudFront Developer Guide* .
               
              * **An ELB load balancer:** Specify the DNS name associated with the load balancer. You can get the DNS name by using the AWS Management Console, the ELB API, or the AWS CLI. Use the same method to get values for ``HostedZoneId`` and ``DNSName`` . If you get one value from the console and the other value from the API or the CLI, creating the resource record set will fail.
               
              * **An Elastic Beanstalk environment:** Specify the CNAME attribute for the environment. (The environment must have a regionalized domain name.) 
               
              * **An Amazon S3 bucket that is configured as a static website:** Specify the domain name of the Amazon S3 website endpoint in which you created the bucket; for example, ``s3-website-us-east-1.amazonaws.com`` . For more information about valid values, see the table `Amazon Simple Storage Service (S3) Website Endpoints`_ in the *Amazon Web Services General Reference* . For more information about using Amazon S3 buckets for websites, see `Hosting a Static Website on Amazon S3`_ in the *Amazon Simple Storage Service Developer Guide* .
               
              * **Another Amazon Route 53 resource record set:** Specify the value of the ``Name`` element for a resource record set in the current hosted zone.
               

               

              For more information and an example, see `Example\: Creating Alias Resource Record Sets`_ in the *Amazon Route 53 API Reference* .

              

              

            EvaluateTargetHealth -> (boolean)

              

              *Alias resource record sets only:* If you set the value of ``EvaluateTargetHealth`` to ``true`` for the resource record set or sets in an alias, weighted alias, latency alias, or failover alias resource record set, and if you specify a value for ``HealthCheckId`` for every resource record set that is referenced by these alias resource record sets, the alias resource record sets inherit the health of the referenced resource record sets.

               

              In this configuration, when Amazon Route 53 receives a DNS query for an alias resource record set:

               

               
              * Amazon Route 53 looks at the resource record sets that are referenced by the alias resource record sets to determine which health checks they're using.
               
              * Amazon Route 53 checks the current status of each health check. (Amazon Route 53 periodically checks the health of the endpoint that is specified in a health check; it doesn't perform the health check when the DNS query arrives.)
               
              * Based on the status of the health checks, Amazon Route 53 determines which resource record sets are healthy. Unhealthy resource record sets are immediately removed from consideration. In addition, if all of the resource record sets that are referenced by an alias resource record set are unhealthy, that alias resource record set also is immediately removed from consideration.
               
              * Based on the configuration of the alias resource record sets (weighted alias or latency alias, for example) and the configuration of the resource record sets that they reference, Amazon Route 53 chooses a resource record set from the healthy resource record sets, and responds to the query.
               

               

              Note the following:

               

              
              * You cannot set ``EvaluateTargetHealth`` to true when the alias target is a CloudFront distribution.
               
              * If the AWS resource that you specify in ``AliasTarget`` is a resource record set or a group of resource record sets (for example, a group of weighted resource record sets), but it is not another alias resource record set, we recommend that you associate a health check with all of the resource record sets in the alias target. For more information, see `What Happens When You Omit Health Checks?`_ in the *Amazon Route 53 Developer Guide* .
               
              * If you specify an ELB load balancer in ``AliasTarget`` , Elastic Load Balancing routes queries only to the healthy Amazon EC2 instances that are registered with the load balancer. If no Amazon EC2 instances are healthy or if the load balancer itself is unhealthy, and if ``EvaluateTargetHealth`` is ``true`` for the corresponding alias resource record set, Amazon Route 53 routes queries to other resources.
               
              * When you create a load balancer, you configure settings for Elastic Load Balancing health checks; they're not Amazon Route 53 health checks, but they perform a similar function. Do not create Amazon Route 53 health checks for the Amazon EC2 instances that you register with an ELB load balancer. For more information, see `How Health Checks Work in More Complex Amazon Route 53 Configurations`_ in the *Amazon Route 53 Developer Guide* .
               

               

              We recommend that you set ``EvaluateTargetHealth`` to ``true`` only when you have enough idle capacity to handle the failure of one or more endpoints.

               

              For more information and examples, see `Amazon Route 53 Health Checks and DNS Failover`_ in the *Amazon Route 53 Developer Guide* .

              

              

            

          HealthCheckId -> (string)

            

            *Health Check resource record sets only, not required for alias resource record sets:* An identifier that is used to identify health check associated with the resource record set.

            

            

          TrafficPolicyInstanceId -> (string)

            

            

          

        

      

    

  

NextMarker -> (string)

  

  The next page marker.

  

  



.. _Example\: Creating Alias Resource Record Sets: http://docs.aws.amazon.com/Route53/latest/APIReference/CreateAliasRRSAPI.html
.. _What Happens When You Omit Health Checks?: http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/dns-failover-complex-configs.html#dns-failover-complex-configs-hc-omitting
.. _Using an Asterisk (*) in the Names of Hosted Zones and Resource Record Sets: http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/DomainNameFormat.html#domain-name-format-asterisk
.. _Hosting a Static Website on Amazon S3: http://docs.aws.amazon.com/AmazonS3/latest/dev/WebsiteHosting.html
.. _Using Alternate Domain Names (CNAMEs): http://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/CNAMEs.html
.. _Supported DNS Resource Record Types: http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/ResourceRecordTypes.html
.. _How Health Checks Work in More Complex Amazon Route 53 Configurations: http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/dns-failover-complex-configs.html
.. _Amazon Simple Storage Service (S3) Website Endpoints: http://docs.aws.amazon.com/general/latest/gr/rande.html#s3_region
.. _DNS Domain Name Format: http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/DomainNameFormat.html
.. _Options for Configuring Amazon Route 53 Active-Active and Active-Passive Failover: http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/dns-failover-configuring-options.html
.. _Amazon Route 53 Health Checks and DNS Failover: http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/dns-failover.html
.. _The SPF DNS Record Type: http://tools.ietf.org/html/rfc7208#section-14.1
