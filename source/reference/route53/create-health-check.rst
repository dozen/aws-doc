[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 create-health-check:


*******************
create-health-check
*******************



===========
Description
===========



This action creates a new health check.

 

To create a new health check, send a ``POST`` request to the ``/*Route 53 API version* /healthcheck`` resource. The request body must include a document with a ``CreateHealthCheckRequest`` element. The response returns the ``CreateHealthCheckResponse`` element that contains metadata about the health check.



========
Synopsis
========

::

    create-health-check
  --caller-reference <value>
  --health-check-config <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--caller-reference`` (string)


  A unique string that identifies the request and that allows failed ``create-health-check`` requests to be retried without the risk of executing the operation twice. You must use a unique ``CallerReference`` string every time you create a health check. ``CallerReference`` can be any unique string; you might choose to use a string that identifies your project.

   

  Valid characters are any Unicode code points that are legal in an XML 1.0 document. The UTF-8 encoding of the value must be less than 128 bytes.

  

``--health-check-config`` (structure)


  A complex type that contains health check configuration.

  



Shorthand Syntax::

    IPAddress=string,Port=integer,Type=string,ResourcePath=string,FullyQualifiedDomainName=string,SearchString=string,RequestInterval=integer,FailureThreshold=integer,MeasureLatency=boolean,Inverted=boolean,HealthThreshold=integer,ChildHealthChecks=string,string,EnableSNI=boolean




JSON Syntax::

  {
    "IPAddress": "string",
    "Port": integer,
    "Type": "HTTP"|"HTTPS"|"HTTP_STR_MATCH"|"HTTPS_STR_MATCH"|"TCP"|"CALCULATED",
    "ResourcePath": "string",
    "FullyQualifiedDomainName": "string",
    "SearchString": "string",
    "RequestInterval": integer,
    "FailureThreshold": integer,
    "MeasureLatency": true|false,
    "Inverted": true|false,
    "HealthThreshold": integer,
    "ChildHealthChecks": ["string", ...],
    "EnableSNI": true|false
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

    

    The ID of the specified health check.

    

    

  CallerReference -> (string)

    

    A unique string that identifies the request to create the health check.

    

    

  HealthCheckConfig -> (structure)

    

    A complex type that contains the health check configuration.

    

    IPAddress -> (string)

      

      IP Address of the instance being checked. 

      

      

    Port -> (integer)

      

      Port on which connection will be opened to the instance to health check. For HTTP and HTTP_STR_MATCH this defaults to 80 if the port is not specified. For HTTPS and HTTPS_STR_MATCH this defaults to 443 if the port is not specified.

      

      

    Type -> (string)

      

      The type of health check to be performed. Currently supported types are TCP, HTTP, HTTPS, HTTP_STR_MATCH, and HTTPS_STR_MATCH.

      

      

    ResourcePath -> (string)

      

      Path to ping on the instance to check the health. Required for HTTP, HTTPS, HTTP_STR_MATCH, and HTTPS_STR_MATCH health checks. The HTTP request is issued to the instance on the given port and path.

      

      

    FullyQualifiedDomainName -> (string)

      

      Fully qualified domain name of the instance to be health checked.

      

      

    SearchString -> (string)

      

      A string to search for in the body of a health check response. Required for HTTP_STR_MATCH and HTTPS_STR_MATCH health checks. Amazon Route 53 considers case when searching for ``SearchString`` in the response body. 

      

      

    RequestInterval -> (integer)

      

      The number of seconds between the time that Amazon Route 53 gets a response from your endpoint and the time that it sends the next health-check request.

       

      Each Amazon Route 53 health checker makes requests at this interval. Valid values are 10 and 30. The default value is 30.

      

      

    FailureThreshold -> (integer)

      

      The number of consecutive health checks that an endpoint must pass or fail for Amazon Route 53 to change the current status of the endpoint from unhealthy to healthy or vice versa.

       

      Valid values are integers between 1 and 10. For more information, see "How Amazon Route 53 Determines Whether an Endpoint Is Healthy" in the Amazon Route 53 Developer Guide.

      

      

    MeasureLatency -> (boolean)

      

      A Boolean value that indicates whether you want Amazon Route 53 to measure the latency between health checkers in multiple AWS regions and your endpoint and to display CloudWatch latency graphs in the Amazon Route 53 console.

      

      

    Inverted -> (boolean)

      

      A boolean value that indicates whether the status of health check should be inverted. For example, if a health check is healthy but ``Inverted`` is ``True`` , then Amazon Route 53 considers the health check to be unhealthy.

      

      

    HealthThreshold -> (integer)

      

      The minimum number of child health checks that must be healthy for Amazon Route 53 to consider the parent health check to be healthy. Valid values are integers between 0 and 256, inclusive.

      

      

    ChildHealthChecks -> (list)

      

      For a specified parent health check, a list of ``HealthCheckId`` values for the associated child health checks.

      

      (string)

        

        

      

    EnableSNI -> (boolean)

      

      Specify whether you want Amazon Route 53 to send the value of ``FullyQualifiedDomainName`` to the endpoint in the ``client_hello`` message during TLS negotiation. If you don't specify a value for ``EnableSNI`` , Amazon Route 53 defaults to ``true`` when ``Type`` is ``HTTPS`` or ``HTTPS_STR_MATCH`` and defaults to ``false`` when ``Type`` is any other value.

      

      

    

  HealthCheckVersion -> (long)

    

    The version of the health check. You can optionally pass this value in a call to ``update-health-check`` to prevent overwriting another change to the health check.

    

    

  

Location -> (string)

  

  The unique URL representing the new health check.

  

  

