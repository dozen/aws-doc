[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 create-health-check:


*******************
create-health-check
*******************



===========
Description
===========



Creates a new health check.

 

For information about adding health checks to resource record sets, see  ResourceRecordSet$HealthCheckId in  change-resource-record-sets . 

 

 **ELB Load Balancers**  

 

If you're registering EC2 instances with an Elastic Load Balancing (ELB) load balancer, do not create Amazon Route 53 health checks for the EC2 instances. When you register an EC2 instance with a load balancer, you configure settings for an ELB health check, which performs a similar function to an Amazon Route 53 health check.

 

 **Private Hosted Zones**  

 

You can associate health checks with failover resource record sets in a private hosted zone. Note the following:

 

 
* Amazon Route 53 health checkers are outside the VPC. To check the health of an endpoint within a VPC by IP address, you must assign a public IP address to the instance in the VPC. 
 
* You can configure a health checker to check the health of an external resource that the instance relies on, such as a database server. 
 
* You can create a CloudWatch metric, associate an alarm with the metric, and then create a health check that is based on the state of the alarm. For example, you might create a CloudWatch metric that checks the status of the Amazon EC2 ``StatusCheckFailed`` metric, add an alarm to the metric, and then create a health check that is based on the state of the alarm. For information about creating CloudWatch metrics and alarms by using the CloudWatch console, see the `Amazon CloudWatch User Guide <http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/WhatIsCloudWatch.html>`_ . 
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53-2013-04-01/CreateHealthCheck>`_


========
Synopsis
========

::

    create-health-check
  --caller-reference <value>
  --health-check-config <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--caller-reference`` (string)


  A unique string that identifies the request and that allows you to retry a failed ``create-health-check`` request without the risk of creating two identical health checks:

   

   
  * If you send a ``create-health-check`` request with the same ``CallerReference`` and settings as a previous request, and if the health check doesn't exist, Amazon Route 53 creates the health check. If the health check does exist, Amazon Route 53 returns the settings for the existing health check. 
   
  * If you send a ``create-health-check`` request with the same ``CallerReference`` as a deleted health check, regardless of the settings, Amazon Route 53 returns a ``HealthCheckAlreadyExists`` error. 
   
  * If you send a ``create-health-check`` request with the same ``CallerReference`` as an existing health check but with different settings, Amazon Route 53 returns a ``HealthCheckAlreadyExists`` error. 
   
  * If you send a ``create-health-check`` request with a unique ``CallerReference`` but settings identical to an existing health check, Amazon Route 53 creates the health check. 
   

  

``--health-check-config`` (structure)


  A complex type that contains the response to a ``create-health-check`` request. 

  



Shorthand Syntax::

    IPAddress=string,Port=integer,Type=string,ResourcePath=string,FullyQualifiedDomainName=string,SearchString=string,RequestInterval=integer,FailureThreshold=integer,MeasureLatency=boolean,Inverted=boolean,HealthThreshold=integer,ChildHealthChecks=string,string,EnableSNI=boolean,Regions=string,string,AlarmIdentifier={Region=string,Name=string},InsufficientDataHealthStatus=string




JSON Syntax::

  {
    "IPAddress": "string",
    "Port": integer,
    "Type": "HTTP"|"HTTPS"|"HTTP_STR_MATCH"|"HTTPS_STR_MATCH"|"TCP"|"CALCULATED"|"CLOUDWATCH_METRIC",
    "ResourcePath": "string",
    "FullyQualifiedDomainName": "string",
    "SearchString": "string",
    "RequestInterval": integer,
    "FailureThreshold": integer,
    "MeasureLatency": true|false,
    "Inverted": true|false,
    "HealthThreshold": integer,
    "ChildHealthChecks": ["string", ...],
    "EnableSNI": true|false,
    "Regions": ["us-east-1"|"us-west-1"|"us-west-2"|"eu-west-1"|"ap-southeast-1"|"ap-southeast-2"|"ap-northeast-1"|"sa-east-1", ...],
    "AlarmIdentifier": {
      "Region": "us-east-1"|"us-east-2"|"us-west-1"|"us-west-2"|"ca-central-1"|"eu-central-1"|"eu-west-1"|"eu-west-2"|"ap-south-1"|"ap-southeast-1"|"ap-southeast-2"|"ap-northeast-1"|"ap-northeast-2"|"sa-east-1",
      "Name": "string"
    },
    "InsufficientDataHealthStatus": "Healthy"|"Unhealthy"|"LastKnownStatus"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a health check**

The following ``create-health-check`` command creates a health check using the caller reference ``2014-04-01-18:47`` and the JSON-formatted configuration in the file ``C:\awscli\route53\create-health-check.json``::

  aws route53 create-health-check --caller-reference 2014-04-01-18:47 --health-check-config file://C:\awscli\route53\create-health-check.json

JSON syntax::

  {
    "IPAddress": "IP address of the endpoint to check",
    "Port": port on the endpoint to check--required when Type is "TCP",
    "Type": "HTTP"|"HTTPS"|"HTTP_STR_MATCH"|"HTTPS_STR_MATCH"|"TCP",
    "ResourcePath": "path of the file that you want Amazon Route 53 to request--all Types except TCP",
    "FullyQualifiedDomainName": "domain name of the endpoint to check--all Types except TCP",
    "SearchString": "if Type is HTTP_STR_MATCH or HTTPS_STR_MATCH, the string to search for in the response body from the specified resource",
    "RequestInterval": 10 | 30,
    "FailureThreshold": integer between 1 and 10
  }


To add the health check to a Route 53 resource record set, use the ``change-resource-record-sets`` command.

For more information, see `Amazon Route 53 Health Checks and DNS Failover`_ in the *Amazon Route 53 Developer Guide*.

.. _`Amazon Route 53 Health Checks and DNS Failover`: http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/dns-failover.html



======
Output
======

HealthCheck -> (structure)

  

  A complex type that contains identifying information about the health check.

  

  Id -> (string)

    

    The identifier that Amazon Route 53assigned to the health check when you created it. When you add or update a resource record set, you use this value to specify which health check to use. The value can be up to 64 characters long. 

    

    

  CallerReference -> (string)

    

    A unique string that you specified when you created the health check.

    

    

  HealthCheckConfig -> (structure)

    

    A complex type that contains detailed information about one health check.

    

    IPAddress -> (string)

      

      The IPv4 or IPv6 IP address of the endpoint that you want Amazon Route 53 to perform health checks on. If you don't specify a value for ``IPAddress`` , Amazon Route 53 sends a DNS request to resolve the domain name that you specify in ``FullyQualifiedDomainName`` at the interval that you specify in ``RequestInterval`` . Using an IP address returned by DNS, Amazon Route 53 then checks the health of the endpoint.

       

      Use one of the following formats for the value of ``IPAddress`` : 

       

       
      * **IPv4 address** : four values between 0 and 255, separated by periods (.), for example, ``192.0.2.44`` . 
       
      * **IPv6 address** : eight groups of four hexadecimal values, separated by colons (:), for example, ``2001:0db8:85a3:0000:0000:abcd:0001:2345`` . You can also shorten IPv6 addresses as described in RFC 5952, for example, ``2001:db8:85a3::abcd:1:2345`` . 
       

       

      If the endpoint is an EC2 instance, we recommend that you create an Elastic IP address, associate it with your EC2 instance, and specify the Elastic IP address for ``IPAddress`` . This ensures that the IP address of your instance will never change.

       

      For more information, see  HealthCheckConfig$FullyQualifiedDomainName .

       

      Constraints: Amazon Route 53 can't check the health of endpoints for which the IP address is in local, private, non-routable, or multicast ranges. For more information about IP addresses for which you can't create health checks, see the following documents:

       

       
      * `RFC 5735, Special Use IPv4 Addresses <https://tools.ietf.org/html/rfc5735>`_   
       
      * `RFC 6598, IANA-Reserved IPv4 Prefix for Shared Address Space <https://tools.ietf.org/html/rfc6598>`_   
       
      * `RFC 5156, Special-Use IPv6 Addresses <https://tools.ietf.org/html/rfc5156>`_   
       

       

      When the value of ``Type`` is ``CALCULATED`` or ``CLOUDWATCH_METRIC`` , omit ``IPAddress`` .

      

      

    Port -> (integer)

      

      The port on the endpoint on which you want Amazon Route 53 to perform health checks. Specify a value for ``Port`` only when you specify a value for ``IPAddress`` .

      

      

    Type -> (string)

      

      The type of health check that you want to create, which indicates how Amazon Route 53 determines whether an endpoint is healthy.

       

      .. warning::

         

        You can't change the value of ``Type`` after you create a health check.

         

       

      You can create the following types of health checks:

       

       
      * **HTTP** : Amazon Route 53 tries to establish a TCP connection. If successful, Amazon Route 53 submits an HTTP request and waits for an HTTP status code of 200 or greater and less than 400. 
       
      * **HTTPS** : Amazon Route 53 tries to establish a TCP connection. If successful, Amazon Route 53 submits an HTTPS request and waits for an HTTP status code of 200 or greater and less than 400. 

      .. warning::

         If you specify ``HTTPS`` for the value of ``Type`` , the endpoint must support TLS v1.0 or later. 

       
       
      * **HTTP_STR_MATCH** : Amazon Route 53 tries to establish a TCP connection. If successful, Amazon Route 53 submits an HTTP request and searches the first 5,120 bytes of the response body for the string that you specify in ``SearchString`` . 
       
      * **HTTPS_STR_MATCH** : Amazon Route 53 tries to establish a TCP connection. If successful, Amazon Route 53 submits an ``HTTPS`` request and searches the first 5,120 bytes of the response body for the string that you specify in ``SearchString`` . 
       
      * **TCP** : Amazon Route 53 tries to establish a TCP connection. 
       
      * **CLOUDWATCH_METRIC** : The health check is associated with a CloudWatch alarm. If the state of the alarm is ``OK`` , the health check is considered healthy. If the state is ``ALARM`` , the health check is considered unhealthy. If CloudWatch doesn't have sufficient data to determine whether the state is ``OK`` or ``ALARM`` , the health check status depends on the setting for ``InsufficientDataHealthStatus`` : ``Healthy`` , ``Unhealthy`` , or ``LastKnownStatus`` .  
       
      * **CALCULATED** : For health checks that monitor the status of other health checks, Amazon Route 53 adds up the number of health checks that Amazon Route 53 health checkers consider to be healthy and compares that number with the value of ``HealthThreshold`` .  
       

       

      For more information, see `How Amazon Route 53 Determines Whether an Endpoint Is Healthy <http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/dns-failover-determining-health-of-endpoints.html>`_ in the *Amazon Route 53 Developer Guide* .

      

      

    ResourcePath -> (string)

      

      The path, if any, that you want Amazon Route 53 to request when performing health checks. The path can be any value for which your endpoint will return an HTTP status code of 2xx or 3xx when the endpoint is healthy, for example, the file /docs/route53-health-check.html. 

      

      

    FullyQualifiedDomainName -> (string)

      

      Amazon Route 53 behavior depends on whether you specify a value for ``IPAddress`` .

       

       **If you specify a value for**  ``IPAddress`` :

       

      Amazon Route 53 sends health check requests to the specified IPv4 or IPv6 address and passes the value of ``FullyQualifiedDomainName`` in the ``Host`` header for all health checks except TCP health checks. This is typically the fully qualified DNS name of the endpoint on which you want Amazon Route 53 to perform health checks.

       

      When Amazon Route 53 checks the health of an endpoint, here is how it constructs the ``Host`` header:

       

       
      * If you specify a value of ``80`` for ``Port`` and ``HTTP`` or ``HTTP_STR_MATCH`` for ``Type`` , Amazon Route 53 passes the value of ``FullyQualifiedDomainName`` to the endpoint in the Host header.  
       
      * If you specify a value of ``443`` for ``Port`` and ``HTTPS`` or ``HTTPS_STR_MATCH`` for ``Type`` , Amazon Route 53 passes the value of ``FullyQualifiedDomainName`` to the endpoint in the ``Host`` header. 
       
      * If you specify another value for ``Port`` and any value except ``TCP`` for ``Type`` , Amazon Route 53 passes ``FullyQualifiedDomainName:Port`` to the endpoint in the ``Host`` header. 
       

       

      If you don't specify a value for ``FullyQualifiedDomainName`` , Amazon Route 53 substitutes the value of ``IPAddress`` in the ``Host`` header in each of the preceding cases.

       

       **If you don't specify a value for ``IPAddress`` ** :

       

      Amazon Route 53 sends a DNS request to the domain that you specify for ``FullyQualifiedDomainName`` at the interval that you specify for ``RequestInterval`` . Using an IPv4 address that DNS returns, Amazon Route 53 then checks the health of the endpoint.

       

      .. note::

         

        If you don't specify a value for ``IPAddress`` , Amazon Route 53 uses only IPv4 to send health checks to the endpoint. If there's no resource record set with a type of A for the name that you specify for ``FullyQualifiedDomainName`` , the health check fails with a "DNS resolution failed" error.

         

       

      If you want to check the health of weighted, latency, or failover resource record sets and you choose to specify the endpoint only by ``FullyQualifiedDomainName`` , we recommend that you create a separate health check for each endpoint. For example, create a health check for each HTTP server that is serving content for www.example.com. For the value of ``FullyQualifiedDomainName`` , specify the domain name of the server (such as us-east-2-www.example.com), not the name of the resource record sets (www.example.com).

       

      .. warning::

         

        In this configuration, if you create a health check for which the value of ``FullyQualifiedDomainName`` matches the name of the resource record sets and you then associate the health check with those resource record sets, health check results will be unpredictable.

         

       

      In addition, if the value that you specify for ``Type`` is ``HTTP`` , ``HTTPS`` , ``HTTP_STR_MATCH`` , or ``HTTPS_STR_MATCH`` , Amazon Route 53 passes the value of ``FullyQualifiedDomainName`` in the ``Host`` header, as it does when you specify a value for ``IPAddress`` . If the value of ``Type`` is ``TCP`` , Amazon Route 53 doesn't pass a ``Host`` header.

      

      

    SearchString -> (string)

      

      If the value of Type is ``HTTP_STR_MATCH`` or ``HTTP_STR_MATCH`` , the string that you want Amazon Route 53 to search for in the response body from the specified resource. If the string appears in the response body, Amazon Route 53 considers the resource healthy.

       

      Amazon Route 53 considers case when searching for ``SearchString`` in the response body. 

      

      

    RequestInterval -> (integer)

      

      The number of seconds between the time that Amazon Route 53 gets a response from your endpoint and the time that it sends the next health check request. Each Amazon Route 53 health checker makes requests at this interval.

       

      .. warning::

         

        You can't change the value of ``RequestInterval`` after you create a health check.

         

       

      If you don't specify a value for ``RequestInterval`` , the default value is ``30`` seconds.

      

      

    FailureThreshold -> (integer)

      

      The number of consecutive health checks that an endpoint must pass or fail for Amazon Route 53 to change the current status of the endpoint from unhealthy to healthy or vice versa. For more information, see `How Amazon Route 53 Determines Whether an Endpoint Is Healthy <http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/dns-failover-determining-health-of-endpoints.html>`_ in the *Amazon Route 53 Developer Guide* .

       

      If you don't specify a value for ``FailureThreshold`` , the default value is three health checks.

      

      

    MeasureLatency -> (boolean)

      

      Specify whether you want Amazon Route 53 to measure the latency between health checkers in multiple AWS regions and your endpoint, and to display CloudWatch latency graphs on the **Health Checks** page in the Amazon Route 53 console.

       

      .. warning::

         

        You can't change the value of ``MeasureLatency`` after you create a health check.

         

      

      

    Inverted -> (boolean)

      

      Specify whether you want Amazon Route 53 to invert the status of a health check, for example, to consider a health check unhealthy when it otherwise would be considered healthy.

      

      

    HealthThreshold -> (integer)

      

      The number of child health checks that are associated with a ``CALCULATED`` health that Amazon Route 53 must consider healthy for the ``CALCULATED`` health check to be considered healthy. To specify the child health checks that you want to associate with a ``CALCULATED`` health check, use the  HealthCheckConfig$ChildHealthChecks and  HealthCheckConfig$ChildHealthChecks elements.

       

      Note the following:

       

       
      * If you specify a number greater than the number of child health checks, Amazon Route 53 always considers this health check to be unhealthy. 
       
      * If you specify ``0`` , Amazon Route 53 always considers this health check to be healthy. 
       

      

      

    ChildHealthChecks -> (list)

      

      (CALCULATED Health Checks Only) A complex type that contains one ``ChildHealthCheck`` element for each health check that you want to associate with a ``CALCULATED`` health check.

      

      (string)

        

        

      

    EnableSNI -> (boolean)

      

      Specify whether you want Amazon Route 53 to send the value of ``FullyQualifiedDomainName`` to the endpoint in the ``client_hello`` message during TLS negotiation. This allows the endpoint to respond to ``HTTPS`` health check requests with the applicable SSL/TLS certificate.

       

      Some endpoints require that ``HTTPS`` requests include the host name in the ``client_hello`` message. If you don't enable SNI, the status of the health check will be ``SSL alert handshake_failure`` . A health check can also have that status for other reasons. If SNI is enabled and you're still getting the error, check the SSL/TLS configuration on your endpoint and confirm that your certificate is valid.

       

      The SSL/TLS certificate on your endpoint includes a domain name in the ``Common Name`` field and possibly several more in the ``Subject Alternative Names`` field. One of the domain names in the certificate should match the value that you specify for ``FullyQualifiedDomainName`` . If the endpoint responds to the ``client_hello`` message with a certificate that does not include the domain name that you specified in ``FullyQualifiedDomainName`` , a health checker will retry the handshake. In the second attempt, the health checker will omit ``FullyQualifiedDomainName`` from the ``client_hello`` message.

      

      

    Regions -> (list)

      

      A complex type that contains one ``Region`` element for each region from which you want Amazon Route 53 health checkers to check the specified endpoint.

       

      If you don't specify any regions, Amazon Route 53 health checkers automatically performs checks from all of the regions that are listed under **Valid Values** .

       

      If you update a health check to remove a region that has been performing health checks, Amazon Route 53 will briefly continue to perform checks from that region to ensure that some health checkers are always checking the endpoint (for example, if you replace three regions with four different regions). 

      

      (string)

        

        

      

    AlarmIdentifier -> (structure)

      

      A complex type that identifies the CloudWatch alarm that you want Amazon Route 53 health checkers to use to determine whether this health check is healthy.

      

      Region -> (string)

        

        A complex type that identifies the CloudWatch alarm that you want Amazon Route 53 health checkers to use to determine whether this health check is healthy.

         

        For the current list of CloudWatch regions, see `Amazon CloudWatch <http://docs.aws.amazon.com/general/latest/gr/rande.html#cw_region>`_ in the *AWS Regions and Endpoints* chapter of the *Amazon Web Services General Reference* .

        

        

      Name -> (string)

        

        The name of the CloudWatch alarm that you want Amazon Route 53 health checkers to use to determine whether this health check is healthy.

        

        

      

    InsufficientDataHealthStatus -> (string)

      

      When CloudWatch has insufficient data about the metric to determine the alarm state, the status that you want Amazon Route 53 to assign to the health check:

       

       
      * ``Healthy`` : Amazon Route 53 considers the health check to be healthy. 
       
      * ``Unhealthy`` : Amazon Route 53 considers the health check to be unhealthy. 
       
      * ``LastKnownStatus`` : Amazon Route 53 uses the status of the health check from the last time that CloudWatch had sufficient data to determine the alarm state. For new health checks that have no last known status, the default status for the health check is healthy. 
       

      

      

    

  HealthCheckVersion -> (long)

    

    The version of the health check. You can optionally pass this value in a call to ``update-health-check`` to prevent overwriting another change to the health check.

    

    

  CloudWatchAlarmConfiguration -> (structure)

    

    A complex type that contains information about the CloudWatch alarm that Amazon Route 53 is monitoring for this health check.

    

    EvaluationPeriods -> (integer)

      

      For the metric that the CloudWatch alarm is associated with, the number of periods that the metric is compared to the threshold.

      

      

    Threshold -> (double)

      

      For the metric that the CloudWatch alarm is associated with, the value the metric is compared with.

      

      

    ComparisonOperator -> (string)

      

      For the metric that the CloudWatch alarm is associated with, the arithmetic operation that is used for the comparison.

      

      

    Period -> (integer)

      

      For the metric that the CloudWatch alarm is associated with, the duration of one evaluation period in seconds.

      

      

    MetricName -> (string)

      

      The name of the CloudWatch metric that the alarm is associated with.

      

      

    Namespace -> (string)

      

      The namespace of the metric that the alarm is associated with. For more information, see `Amazon CloudWatch Namespaces, Dimensions, and Metrics Reference <http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html>`_ in the *Amazon CloudWatch User Guide* .

      

      

    Statistic -> (string)

      

      For the metric that the CloudWatch alarm is associated with, the statistic that is applied to the metric.

      

      

    Dimensions -> (list)

      

      For the metric that the CloudWatch alarm is associated with, a complex type that contains information about the dimensions for the metric. For information, see `Amazon CloudWatch Namespaces, Dimensions, and Metrics Reference <http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/CW_Support_For_AWS.html>`_ in the *Amazon CloudWatch User Guide* .

      

      (structure)

        

        For the metric that the CloudWatch alarm is associated with, a complex type that contains information about one dimension.

        

        Name -> (string)

          

          For the metric that the CloudWatch alarm is associated with, the name of one dimension.

          

          

        Value -> (string)

          

          For the metric that the CloudWatch alarm is associated with, the value of one dimension.

          

          

        

      

    

  

Location -> (string)

  

  The unique URL representing the new health check.

  

  

