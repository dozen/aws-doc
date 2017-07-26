[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 list-resource-record-sets:


*************************
list-resource-record-sets
*************************



===========
Description
===========



Lists the resource record sets in a specified hosted zone.

 

 ``list-resource-record-sets`` returns up to 100 resource record sets at a time in ASCII order, beginning at a position specified by the ``name`` and ``type`` elements. The action sorts results first by DNS name with the labels reversed, for example:

 

 ``com.example.www.``  

 

Note the trailing dot, which can change the sort order in some circumstances.

 

When multiple records have the same DNS name, the action sorts results by the record type.

 

You can use the name and type elements to adjust the beginning position of the list of resource record sets returned:

  If you do not specify Name or Type  

The results begin with the first resource record set that the hosted zone contains.

  If you specify Name but not Type  

The results begin with the first resource record set in the list whose name is greater than or equal to ``Name`` .

  If you specify Type but not Name  

Amazon Route 53 returns the ``InvalidInput`` error.

  If you specify both Name and Type  

The results begin with the first resource record set in the list whose name is greater than or equal to ``Name`` , and whose type is greater than or equal to ``Type`` .

   

This action returns the most current version of the records. This includes records that are ``PENDING`` , and that are not yet available on all Amazon Route 53 DNS servers.

 

To ensure that you get an accurate listing of the resource record sets for a hosted zone at a point in time, do not submit a ``change-resource-record-sets`` request while you're paging through the results of a ``list-resource-record-sets`` request. If you do, some pages may display results without the latest changes while other pages display results with the latest changes.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53-2013-04-01/ListResourceRecordSets>`_


``list-resource-record-sets`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``ResourceRecordSets``


========
Synopsis
========

::

    list-resource-record-sets
  --hosted-zone-id <value>
  [--max-items <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--hosted-zone-id`` (string)


  The ID of the hosted zone that contains the resource record sets that you want to list.

  

``--max-items`` (string)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (string)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To list the resource record sets in a hosted zone**

The following ``list-resource-record-sets`` command lists summary information about the first 100 resource record sets in a specified hosted zone.::

  aws route53 list-resource-record-sets --hosted-zone-id Z2LD58HEXAMPLE

If the hosted zone contains more than 100 resource record sets, or if you want to list them in groups smaller than 100, include the ``--maxitems`` parameter. For example, to list resource record sets one at a time, use the following command::

  aws route53 list-resource-record-sets --hosted-zone-id Z2LD58HEXAMPLE --max-items 1

To view information about the next resource record set in the hosted zone, take the value of ``NextToken`` from the response to the previous command, and include it in the ``--starting-token`` parameter, for example::

  aws route53 list-resource-record-sets --hosted-zone-id Z2LD58HEXAMPLE --max-items 1 --starting-token Z3M3LMPEXAMPLE

To view all the resource record sets of a particular name, use the ``--query`` parameter to filter them out. For example::

  aws route53 list-resource-record-sets --hosted-zone-id Z2LD58HEXAMPLE --query "ResourceRecordSets[?Name == 'example.domain.']"



======
Output
======

ResourceRecordSets -> (list)

  

  Information about multiple resource record sets.

  

  (structure)

    

    Information about the resource record set to create or delete.

    

    Name -> (string)

      

      The name of the domain you want to perform the action on.

       

      Enter a fully qualified domain name, for example, ``www.example.com`` . You can optionally include a trailing dot. If you omit the trailing dot, Amazon Route 53 still assumes that the domain name that you specify is fully qualified. This means that Amazon Route 53 treats ``www.example.com`` (without a trailing dot) and ``www.example.com.`` (with a trailing dot) as identical.

       

      For information about how to specify characters other than ``a-z`` , ``0-9`` , and ``-`` (hyphen) and how to specify internationalized domain names, see `DNS Domain Name Format <http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/DomainNameFormat.html>`_ in the *Amazon Route 53 Developer Guide* .

       

      You can use the asterisk (*) wildcard to replace the leftmost label in a domain name, for example, ``*.example.com`` . Note the following:

       

       
      * The * must replace the entire label. For example, you can't specify ``*prod.example.com`` or ``prod*.example.com`` . 
       
      * The * can't replace any of the middle labels, for example, marketing.*.example.com. 
       
      * If you include * in any position other than the leftmost label in a domain name, DNS treats it as an * character (ASCII 42), not as a wildcard. 

      .. warning::

         You can't use the * wildcard for resource records sets that have a type of NS. 

       
       

       

      You can use the * wildcard as the leftmost label in a domain name, for example, ``*.example.com`` . You can't use an * for one of the middle labels, for example, ``marketing.*.example.com`` . In addition, the * must replace the entire label; for example, you can't specify ``prod*.example.com`` .

      

      

    Type -> (string)

      

      The DNS record type. For information about different record types and how data is encoded for them, see `Supported DNS Resource Record Types <http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/ResourceRecordTypes.html>`_ in the *Amazon Route 53 Developer Guide* .

       

      Valid values for basic resource record sets: ``A`` | ``AAAA`` | ``CNAME`` | ``MX`` | ``NAPTR`` | ``NS`` | ``PTR`` | ``SOA`` | ``SPF`` | ``SRV`` | ``TXT``  

       

      Values for weighted, latency, geolocation, and failover resource record sets: ``A`` | ``AAAA`` | ``CNAME`` | ``MX`` | ``NAPTR`` | ``PTR`` | ``SPF`` | ``SRV`` | ``TXT`` . When creating a group of weighted, latency, geolocation, or failover resource record sets, specify the same value for all of the resource record sets in the group.

       

      Valid values for multivalue answer resource record sets: ``A`` | ``AAAA`` | ``MX`` | ``NAPTR`` | ``PTR`` | ``SPF`` | ``SRV`` | ``TXT``  

       

      .. note::

         

        SPF records were formerly used to verify the identity of the sender of email messages. However, we no longer recommend that you create resource record sets for which the value of ``Type`` is ``SPF`` . RFC 7208, *Sender Policy Framework (SPF) for Authorizing Use of Domains in Email, Version 1* , has been updated to say, "...[I]ts existence and mechanism defined in [RFC4408] have led to some interoperability issues. Accordingly, its use is no longer appropriate for SPF version 1; implementations are not to use it." In RFC 7208, see section 14.1, `The SPF DNS Record Type <http://tools.ietf.org/html/rfc7208#section-14.1>`_ .

         

       

      Values for alias resource record sets:

       

       
      * **CloudFront distributions:**  ``A``   If IPv6 is enabled for the distribution, create two resource record sets to route traffic to your distribution, one with a value of ``A`` and one with a value of ``AAAA`` .  
       
      * **AWS Elastic Beanstalk environment that has a regionalized subdomain** : ``A``   
       
      * **ELB load balancers:**  ``A`` | ``AAAA``   
       
      * **Amazon S3 buckets:**  ``A``   
       
      * **Another resource record set in this hosted zone:** Specify the type of the resource record set that you're creating the alias for. All values are supported except ``NS`` and ``SOA`` . 
       

      

      

    SetIdentifier -> (string)

      

       *Weighted, Latency, Geo, and Failover resource record sets only:* An identifier that differentiates among multiple resource record sets that have the same combination of DNS name and type. The value of ``SetIdentifier`` must be unique for each resource record set that has the same combination of DNS name and type. Omit ``SetIdentifier`` for any other types of record sets.

      

      

    Weight -> (long)

      

       *Weighted resource record sets only:* Among resource record sets that have the same combination of DNS name and type, a value that determines the proportion of DNS queries that Amazon Route 53 responds to using the current resource record set. Amazon Route 53 calculates the sum of the weights for the resource record sets that have the same combination of DNS name and type. Amazon Route 53 then responds to queries based on the ratio of a resource's weight to the total. Note the following:

       

       
      * You must specify a value for the ``Weight`` element for every weighted resource record set. 
       
      * You can only specify one ``ResourceRecord`` per weighted resource record set. 
       
      * You can't create latency, failover, or geolocation resource record sets that have the same values for the ``Name`` and ``Type`` elements as weighted resource record sets. 
       
      * You can create a maximum of 100 weighted resource record sets that have the same values for the ``Name`` and ``Type`` elements. 
       
      * For weighted (but not weighted alias) resource record sets, if you set ``Weight`` to ``0`` for a resource record set, Amazon Route 53 never responds to queries with the applicable value for that resource record set. However, if you set ``Weight`` to ``0`` for all resource record sets that have the same combination of DNS name and type, traffic is routed to all resources with equal probability. The effect of setting ``Weight`` to ``0`` is different when you associate health checks with weighted resource record sets. For more information, see `Options for Configuring Amazon Route 53 Active-Active and Active-Passive Failover <http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/dns-failover-configuring-options.html>`_ in the *Amazon Route 53 Developer Guide* . 
       

      

      

    Region -> (string)

      

       *Latency-based resource record sets only:* The Amazon EC2 Region where you created the resource that this resource record set refers to. The resource typically is an AWS resource, such as an EC2 instance or an ELB load balancer, and is referred to by an IP address or a DNS domain name, depending on the record type.

       

      .. note::

         

        Creating latency and latency alias resource record sets in private hosted zones is not supported.

         

       

      When Amazon Route 53 receives a DNS query for a domain name and type for which you have created latency resource record sets, Amazon Route 53 selects the latency resource record set that has the lowest latency between the end user and the associated Amazon EC2 Region. Amazon Route 53 then returns the value that is associated with the selected resource record set.

       

      Note the following:

       

       
      * You can only specify one ``ResourceRecord`` per latency resource record set. 
       
      * You can only create one latency resource record set for each Amazon EC2 Region. 
       
      * You aren't required to create latency resource record sets for all Amazon EC2 Regions. Amazon Route 53 will choose the region with the best latency from among the regions that you create latency resource record sets for. 
       
      * You can't create non-latency resource record sets that have the same values for the ``Name`` and ``Type`` elements as latency resource record sets. 
       

      

      

    GeoLocation -> (structure)

      

       *Geo location resource record sets only:* A complex type that lets you control how Amazon Route 53 responds to DNS queries based on the geographic origin of the query. For example, if you want all queries from Africa to be routed to a web server with an IP address of ``192.0.2.111`` , create a resource record set with a ``Type`` of ``A`` and a ``ContinentCode`` of ``AF`` .

       

      .. note::

         

        Creating geolocation and geolocation alias resource record sets in private hosted zones is not supported.

         

       

      If you create separate resource record sets for overlapping geographic regions (for example, one resource record set for a continent and one for a country on the same continent), priority goes to the smallest geographic region. This allows you to route most queries for a continent to one resource and to route queries for a country on that continent to a different resource.

       

      You can't create two geolocation resource record sets that specify the same geographic location.

       

      The value ``*`` in the ``CountryCode`` element matches all geographic locations that aren't specified in other geolocation resource record sets that have the same values for the ``Name`` and ``Type`` elements.

       

      .. warning::

         

        Geolocation works by mapping IP addresses to locations. However, some IP addresses aren't mapped to geographic locations, so even if you create geolocation resource record sets that cover all seven continents, Amazon Route 53 will receive some DNS queries from locations that it can't identify. We recommend that you create a resource record set for which the value of ``CountryCode`` is ``*`` , which handles both queries that come from locations for which you haven't created geolocation resource record sets and queries from IP addresses that aren't mapped to a location. If you don't create a ``*`` resource record set, Amazon Route 53 returns a "no answer" response for queries from those locations.

         

       

      You can't create non-geolocation resource record sets that have the same values for the ``Name`` and ``Type`` elements as geolocation resource record sets.

      

      ContinentCode -> (string)

        

        The two-letter code for the continent.

         

        Valid values: ``AF`` | ``AN`` | ``AS`` | ``EU`` | ``OC`` | ``NA`` | ``SA``  

         

        Constraint: Specifying ``ContinentCode`` with either ``CountryCode`` or ``SubdivisionCode`` returns an ``InvalidInput`` error.

        

        

      CountryCode -> (string)

        

        The two-letter code for the country.

        

        

      SubdivisionCode -> (string)

        

        The code for the subdivision, for example, a state in the United States or a province in Canada.

        

        

      

    Failover -> (string)

      

       *Failover resource record sets only:* To configure failover, you add the ``Failover`` element to two resource record sets. For one resource record set, you specify ``PRIMARY`` as the value for ``Failover`` ; for the other resource record set, you specify ``SECONDARY`` . In addition, you include the ``HealthCheckId`` element and specify the health check that you want Amazon Route 53 to perform for each resource record set.

       

      Except where noted, the following failover behaviors assume that you have included the ``HealthCheckId`` element in both resource record sets:

       

       
      * When the primary resource record set is healthy, Amazon Route 53 responds to DNS queries with the applicable value from the primary resource record set regardless of the health of the secondary resource record set. 
       
      * When the primary resource record set is unhealthy and the secondary resource record set is healthy, Amazon Route 53 responds to DNS queries with the applicable value from the secondary resource record set. 
       
      * When the secondary resource record set is unhealthy, Amazon Route 53 responds to DNS queries with the applicable value from the primary resource record set regardless of the health of the primary resource record set. 
       
      * If you omit the ``HealthCheckId`` element for the secondary resource record set, and if the primary resource record set is unhealthy, Amazon Route 53 always responds to DNS queries with the applicable value from the secondary resource record set. This is true regardless of the health of the associated endpoint. 
       

       

      You can't create non-failover resource record sets that have the same values for the ``Name`` and ``Type`` elements as failover resource record sets.

       

      For failover alias resource record sets, you must also include the ``EvaluateTargetHealth`` element and set the value to true.

       

      For more information about configuring failover for Amazon Route 53, see the following topics in the *Amazon Route 53 Developer Guide* : 

       

       
      * `Amazon Route 53 Health Checks and DNS Failover <http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/dns-failover.html>`_   
       
      * `Configuring Failover in a Private Hosted Zone <http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/dns-failover-private-hosted-zones.html>`_   
       

      

      

    MultiValueAnswer -> (boolean)

      

       *Multivalue answer resource record sets only* : To route traffic approximately randomly to multiple resources, such as web servers, create one multivalue answer record for each resource and specify ``true`` for ``MultiValueAnswer`` . Note the following:

       

       
      * If you associate a health check with a multivalue answer resource record set, Amazon Route 53 responds to DNS queries with the corresponding IP address only when the health check is healthy. 
       
      * If you don't associate a health check with a multivalue answer record, Amazon Route 53 always considers the record to be healthy. 
       
      * Amazon Route 53 responds to DNS queries with up to eight healthy records; if you have eight or fewer healthy records, Amazon Route 53 responds to all DNS queries with all the healthy records. 
       
      * If you have more than eight healthy records, Amazon Route 53 responds to different DNS resolvers with different combinations of healthy records. 
       
      * When all records are unhealthy, Amazon Route 53 responds to DNS queries with up to eight unhealthy records. 
       
      * If a resource becomes unavailable after a resolver caches a response, client software typically tries another of the IP addresses in the response. 
       

       

      You can't create multivalue answer alias records.

      

      

    TTL -> (long)

      

      The resource record cache time to live (TTL), in seconds. Note the following:

       

       
      * If you're creating or updating an alias resource record set, omit ``TTL`` . Amazon Route 53 uses the value of ``TTL`` for the alias target.  
       
      * If you're associating this resource record set with a health check (if you're adding a ``HealthCheckId`` element), we recommend that you specify a ``TTL`` of 60 seconds or less so clients respond quickly to changes in health status. 
       
      * All of the resource record sets in a group of weighted resource record sets must have the same value for ``TTL`` . 
       
      * If a group of weighted resource record sets includes one or more weighted alias resource record sets for which the alias target is an ELB load balancer, we recommend that you specify a ``TTL`` of 60 seconds for all of the non-alias weighted resource record sets that have the same name and type. Values other than 60 seconds (the TTL for load balancers) will change the effect of the values that you specify for ``Weight`` . 
       

      

      

    ResourceRecords -> (list)

      

      Information about the resource records to act upon.

       

      .. note::

         

        If you're creating an alias resource record set, omit ``ResourceRecords`` .

         

      

      (structure)

        

        Information specific to the resource record.

         

        .. note::

           

          If you're creating an alias resource record set, omit ``ResourceRecord`` .

           

        

        Value -> (string)

          

          The current or new DNS record value, not to exceed 4,000 characters. In the case of a ``DELETE`` action, if the current value does not match the actual value, an error is returned. For descriptions about how to format ``Value`` for different record types, see `Supported DNS Resource Record Types <http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/ResourceRecordTypes.html>`_ in the *Amazon Route 53 Developer Guide* .

           

          You can specify more than one value for all record types except ``CNAME`` and ``SOA`` . 

           

          .. note::

             

            If you're creating an alias resource record set, omit ``Value`` .

             

          

          

        

      

    AliasTarget -> (structure)

      

       *Alias resource record sets only:* Information about the CloudFront distribution, AWS Elastic Beanstalk environment, ELB load balancer, Amazon S3 bucket, or Amazon Route 53 resource record set to which you're redirecting queries. The AWS Elastic Beanstalk environment must have a regionalized subdomain.

       

      If you're creating resource records sets for a private hosted zone, note the following:

       

       
      * You can't create alias resource record sets for CloudFront distributions in a private hosted zone. 
       
      * Creating geolocation alias resource record sets or latency alias resource record sets in a private hosted zone is unsupported. 
       
      * For information about creating failover resource record sets in a private hosted zone, see `Configuring Failover in a Private Hosted Zone <http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/dns-failover-private-hosted-zones.html>`_ in the *Amazon Route 53 Developer Guide* . 
       

      

      HostedZoneId -> (string)

        

         *Alias resource records sets only* : The value used depends on where you want to route traffic:

          CloudFront distribution  

        Specify ``Z2FDTNDATAQYW2`` .

         

        .. note::

           

          Alias resource record sets for CloudFront can't be created in a private zone.

           

          Elastic Beanstalk environment  

        Specify the hosted zone ID for the region in which you created the environment. The environment must have a regionalized subdomain. For a list of regions and the corresponding hosted zone IDs, see `AWS Elastic Beanstalk <http://docs.aws.amazon.com/general/latest/gr/rande.html#elasticbeanstalk_region>`_ in the "AWS Regions and Endpoints" chapter of the *Amazon Web Services General Reference* .

          ELB load balancer  

        Specify the value of the hosted zone ID for the load balancer. Use the following methods to get the hosted zone ID:

         

         
        * `Elastic Load Balancing <http://docs.aws.amazon.com/general/latest/gr/rande.html#elb_region>`_ table in the "AWS Regions and Endpoints" chapter of the *Amazon Web Services General Reference* : Use the value in the "Amazon Route 53 Hosted Zone ID" column that corresponds with the region that you created your load balancer in. 
         
        * **AWS Management Console** : Go to the Amazon EC2 page, click **Load Balancers** in the navigation pane, select the load balancer, and get the value of the **Hosted zone** field on the **Description** tab. 
         
        * **Elastic Load Balancing API** : Use ``DescribeLoadBalancers`` to get the value of ``CanonicalHostedZoneNameId`` . For more information, see the applicable guide: 

           
          * Classic Load Balancer: `DescribeLoadBalancers <http://docs.aws.amazon.com/elasticloadbalancing/2012-06-01/APIReference/API_DescribeLoadBalancers.html>`_   
           
          * Application Load Balancer: `DescribeLoadBalancers <http://docs.aws.amazon.com/elasticloadbalancing/latest/APIReference/API_DescribeLoadBalancers.html>`_   
           

         
         
        * **AWS CLI** : Use `` `describe-load-balancers <http://docs.aws.amazon.com/cli/latest/reference/elb/describe-load-balancers.html>`_ `` to get the value of ``CanonicalHostedZoneNameID`` . 
         

          An Amazon S3 bucket configured as a static website  

        Specify the hosted zone ID for the region that you created the bucket in. For more information about valid values, see the `Amazon Simple Storage Service Website Endpoints <http://docs.aws.amazon.com/general/latest/gr/rande.html#s3_region>`_ table in the "AWS Regions and Endpoints" chapter of the *Amazon Web Services General Reference* .

          Another Amazon Route 53 resource record set in your hosted zone  

        Specify the hosted zone ID of your hosted zone. (An alias resource record set can't reference a resource record set in a different hosted zone.)

          

        

      DNSName -> (string)

        

         *Alias resource record sets only:* The value that you specify depends on where you want to route queries:

          CloudFront distribution  

        Specify the domain name that CloudFront assigned when you created your distribution.

         

        Your CloudFront distribution must include an alternate domain name that matches the name of the resource record set. For example, if the name of the resource record set is *acme.example.com* , your CloudFront distribution must include *acme.example.com* as one of the alternate domain names. For more information, see `Using Alternate Domain Names (CNAMEs) <http://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/CNAMEs.html>`_ in the *Amazon CloudFront Developer Guide* .

          Elastic Beanstalk environment  

        Specify the ``CNAME`` attribute for the environment. (The environment must have a regionalized domain name.) You can use the following methods to get the value of the CNAME attribute:

         

         
        * *AWS Management Console* : For information about how to get the value by using the console, see `Using Custom Domains with AWS Elastic Beanstalk <http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/customdomains.html>`_ in the *AWS Elastic Beanstalk Developer Guide* . 
         
        * *Elastic Beanstalk API* : Use the ``DescribeEnvironments`` action to get the value of the ``CNAME`` attribute. For more information, see `DescribeEnvironments <http://docs.aws.amazon.com/elasticbeanstalk/latest/api/API_DescribeEnvironments.html>`_ in the *AWS Elastic Beanstalk API Reference* . 
         
        * *AWS CLI* : Use the ``describe-environments`` command to get the value of the ``CNAME`` attribute. For more information, see `describe-environments <http://docs.aws.amazon.com/cli/latest/reference/elasticbeanstalk/describe-environments.html>`_ in the *AWS Command Line Interface Reference* . 
         

          ELB load balancer  

        Specify the DNS name that is associated with the load balancer. Get the DNS name by using the AWS Management Console, the ELB API, or the AWS CLI. 

         

         
        * **AWS Management Console** : Go to the EC2 page, choose **Load Balancers** in the navigation pane, choose the load balancer, choose the **Description** tab, and get the value of the **DNS name** field. (If you're routing traffic to a Classic Load Balancer, get the value that begins with **dualstack** .)  
         
        * **Elastic Load Balancing API** : Use ``DescribeLoadBalancers`` to get the value of ``start-record-name`` . For more information, see the applicable guide: 

           
          * Classic Load Balancer: `DescribeLoadBalancers <http://docs.aws.amazon.com/elasticloadbalancing/2012-06-01/APIReference/API_DescribeLoadBalancers.html>`_   
           
          * Application Load Balancer: `DescribeLoadBalancers <http://docs.aws.amazon.com/elasticloadbalancing/latest/APIReference/API_DescribeLoadBalancers.html>`_   
           

         
         
        * **AWS CLI** : Use `` `describe-load-balancers <http://docs.aws.amazon.com/cli/latest/reference/elb/describe-load-balancers.html>`_ `` to get the value of ``start-record-name`` . 
         

          Amazon S3 bucket that is configured as a static website  

        Specify the domain name of the Amazon S3 website endpoint in which you created the bucket, for example, ``s3-website-us-east-2.amazonaws.com`` . For more information about valid values, see the table `Amazon Simple Storage Service (S3) Website Endpoints <http://docs.aws.amazon.com/general/latest/gr/rande.html#s3_region>`_ in the *Amazon Web Services General Reference* . For more information about using S3 buckets for websites, see `Getting Started with Amazon Route 53 <http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/getting-started.html>`_ in the *Amazon Route 53 Developer Guide.*  

          Another Amazon Route 53 resource record set  

        Specify the value of the ``Name`` element for a resource record set in the current hosted zone.

          

        

      EvaluateTargetHealth -> (boolean)

        

         *Applies only to alias, failover alias, geolocation alias, latency alias, and weighted alias resource record sets:* When ``EvaluateTargetHealth`` is ``true`` , an alias resource record set inherits the health of the referenced AWS resource, such as an ELB load balancer, or the referenced resource record set.

         

        Note the following:

         

         
        * You can't set ``EvaluateTargetHealth`` to ``true`` when the alias target is a CloudFront distribution. 
         
        * If the AWS resource that you specify in ``AliasTarget`` is a resource record set or a group of resource record sets (for example, a group of weighted resource record sets), but it is not another alias resource record set, we recommend that you associate a health check with all of the resource record sets in the alias target. For more information, see `What Happens When You Omit Health Checks? <http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/dns-failover-complex-configs.html#dns-failover-complex-configs-hc-omitting>`_ in the *Amazon Route 53 Developer Guide* . 
         
        * If you specify an Elastic Beanstalk environment in ``HostedZoneId`` and ``start-record-name`` , and if the environment contains an ELB load balancer, Elastic Load Balancing routes queries only to the healthy Amazon EC2 instances that are registered with the load balancer. (An environment automatically contains an ELB load balancer if it includes more than one EC2 instance.) If you set ``EvaluateTargetHealth`` to ``true`` and either no EC2 instances are healthy or the load balancer itself is unhealthy, Amazon Route 53 routes queries to other available resources that are healthy, if any. If the environment contains a single EC2 instance, there are no special requirements. 
         
        * If you specify an ELB load balancer in ``  AliasTarget `` , ELB routes queries only to the healthy EC2 instances that are registered with the load balancer. If no EC2 instances are healthy or if the load balancer itself is unhealthy, and if ``EvaluateTargetHealth`` is true for the corresponding alias resource record set, Amazon Route 53 routes queries to other resources. When you create a load balancer, you configure settings for ELB health checks; they're not Amazon Route 53 health checks, but they perform a similar function. Do not create Amazon Route 53 health checks for the EC2 instances that you register with an ELB load balancer. For more information, see `How Health Checks Work in More Complex Amazon Route 53 Configurations <http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/dns-failover-complex-configs.html>`_ in the *Amazon Route 53 Developer Guide* . 
         
        * We recommend that you set ``EvaluateTargetHealth`` to true only when you have enough idle capacity to handle the failure of one or more endpoints. 
         

         

        For more information and examples, see `Amazon Route 53 Health Checks and DNS Failover <http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/dns-failover.html>`_ in the *Amazon Route 53 Developer Guide* .

        

        

      

    HealthCheckId -> (string)

      

      If you want Amazon Route 53 to return this resource record set in response to a DNS query only when a health check is passing, include the ``HealthCheckId`` element and specify the ID of the applicable health check.

       

      Amazon Route 53 determines whether a resource record set is healthy based on one of the following:

       

       
      * By periodically sending a request to the endpoint that is specified in the health check 
       
      * By aggregating the status of a specified group of health checks (calculated health checks) 
       
      * By determining the current state of a CloudWatch alarm (CloudWatch metric health checks) 
       

       

      For more information, see `How Amazon Route 53 Determines Whether an Endpoint Is Healthy <http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/dns-failover-determining-health-of-endpoints.html>`_ .

       

      The ``HealthCheckId`` element is only useful when Amazon Route 53 is choosing between two or more resource record sets to respond to a DNS query, and you want Amazon Route 53 to base the choice in part on the status of a health check. Configuring health checks only makes sense in the following configurations:

       

       
      * You're checking the health of the resource record sets in a group of weighted, latency, geolocation, or failover resource record sets, and you specify health check IDs for all of the resource record sets. If the health check for one resource record set specifies an endpoint that is not healthy, Amazon Route 53 stops responding to queries using the value for that resource record set. 
       
      * You set ``EvaluateTargetHealth`` to true for the resource record sets in a group of alias, weighted alias, latency alias, geolocation alias, or failover alias resource record sets, and you specify health check IDs for all of the resource record sets that are referenced by the alias resource record sets. 
       

       

      .. warning::

         

        Amazon Route 53 doesn't check the health of the endpoint specified in the resource record set, for example, the endpoint specified by the IP address in the ``Value`` element. When you add a ``HealthCheckId`` element to a resource record set, Amazon Route 53 checks the health of the endpoint that you specified in the health check. 

         

       

      For geolocation resource record sets, if an endpoint is unhealthy, Amazon Route 53 looks for a resource record set for the larger, associated geographic region. For example, suppose you have resource record sets for a state in the United States, for the United States, for North America, and for all locations. If the endpoint for the state resource record set is unhealthy, Amazon Route 53 checks the resource record sets for the United States, for North America, and for all locations (a resource record set for which the value of ``CountryCode`` is ``*`` ), in that order, until it finds a resource record set for which the endpoint is healthy. 

       

      If your health checks specify the endpoint only by domain name, we recommend that you create a separate health check for each endpoint. For example, create a health check for each ``HTTP`` server that is serving content for ``www.example.com`` . For the value of ``FullyQualifiedDomainName`` , specify the domain name of the server (such as ``us-east-2-www.example.com`` ), not the name of the resource record sets (example.com).

       

      .. warning::

         

        n this configuration, if you create a health check for which the value of ``FullyQualifiedDomainName`` matches the name of the resource record sets and then associate the health check with those resource record sets, health check results will be unpredictable.

         

       

      For more information, see the following topics in the *Amazon Route 53 Developer Guide* :

       

       
      * `Amazon Route 53 Health Checks and DNS Failover <http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/dns-failover.html>`_   
       
      * `Configuring Failover in a Private Hosted Zone <http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/dns-failover-private-hosted-zones.html>`_   
       

      

      

    TrafficPolicyInstanceId -> (string)

      

      When you create a traffic policy instance, Amazon Route 53 automatically creates a resource record set. ``TrafficPolicyInstanceId`` is the ID of the traffic policy instance that Amazon Route 53 created this resource record set for.

       

      .. warning::

         

        To delete the resource record set that is associated with a traffic policy instance, use ``delete-traffic-policy-instance`` . Amazon Route 53 will delete the resource record set automatically. If you delete the resource record set by using ``change-resource-record-sets`` , Amazon Route 53 doesn't automatically delete the traffic policy instance, and you'll continue to be charged for it even though it's no longer in use. 

         

      

      

    

  

IsTruncated -> (boolean)

  

  A flag that indicates whether more resource record sets remain to be listed. If your results were truncated, you can make a follow-up pagination request by using the ``NextRecordName`` element.

  

  

NextRecordName -> (string)

  

  If the results were truncated, the name of the next record in the list.

   

  This element is present only if ``IsTruncated`` is true. 

  

  

NextRecordType -> (string)

  

  If the results were truncated, the type of the next record in the list.

   

  This element is present only if ``IsTruncated`` is true. 

  

  

NextRecordIdentifier -> (string)

  

   *Weighted, latency, geolocation, and failover resource record sets only* : If results were truncated for a given DNS name and type, the value of ``SetIdentifier`` for the next resource record set that has the current DNS name and type.

  

  

MaxItems -> (string)

  

  The maximum number of records you requested.

  

  

