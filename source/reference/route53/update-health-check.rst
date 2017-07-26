[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 update-health-check:


*******************
update-health-check
*******************



===========
Description
===========



This action updates an existing health check.

 

To update a health check, send a ``POST`` request to the ``/*Route 53 API version* /healthcheck/*health check ID*`` resource. The request body must include a document with an ``UpdateHealthCheckRequest`` element. The response returns an ``UpdateHealthCheckResponse`` element, which contains metadata about the health check.



========
Synopsis
========

::

    update-health-check
  --health-check-id <value>
  [--health-check-version <value>]
  [--ip-address <value>]
  [--port <value>]
  [--resource-path <value>]
  [--fully-qualified-domain-name <value>]
  [--search-string <value>]
  [--failure-threshold <value>]
  [--inverted | --no-inverted]
  [--health-threshold <value>]
  [--child-health-checks <value>]
  [--enable-sni | --no-enable-sni]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--health-check-id`` (string)


  The ID of the health check to update.

  

``--health-check-version`` (long)


  Optional. When you specify a health check version, Amazon Route 53 compares this value with the current value in the health check, which prevents you from updating the health check when the versions don't match. Using ``health-check-version`` lets you prevent overwriting another change to the health check.

  

``--ip-address`` (string)


  The IP address of the resource that you want to check.

   

  Specify this value only if you want to change it.

  

``--port`` (integer)


  The port on which you want Amazon Route 53 to open a connection to perform health checks.

   

  Specify this value only if you want to change it.

  

``--resource-path`` (string)


  The path that you want Amazon Route 53 to request when performing health checks. The path can be any value for which your endpoint will return an HTTP status code of 2xx or 3xx when the endpoint is healthy, for example the file /docs/route53-health-check.html. 

   

  Specify this value only if you want to change it.

  

``--fully-qualified-domain-name`` (string)


  Fully qualified domain name of the instance to be health checked.

   

  Specify this value only if you want to change it.

  

``--search-string`` (string)


  If the value of ``Type`` is ``HTTP_STR_MATCH`` or ``HTTP_STR_MATCH`` , the string that you want Amazon Route 53 to search for in the response body from the specified resource. If the string appears in the response body, Amazon Route 53 considers the resource healthy. Amazon Route 53 considers case when searching for ``search-string`` in the response body.

   

  Specify this value only if you want to change it.

  

``--failure-threshold`` (integer)


  The number of consecutive health checks that an endpoint must pass or fail for Amazon Route 53 to change the current status of the endpoint from unhealthy to healthy or vice versa.

   

  Valid values are integers between 1 and 10. For more information, see "How Amazon Route 53 Determines Whether an Endpoint Is Healthy" in the Amazon Route 53 Developer Guide.

   

  Specify this value only if you want to change it.

  

``--inverted`` | ``--no-inverted`` (boolean)


  A boolean value that indicates whether the status of health check should be inverted. For example, if a health check is healthy but ``no-inverted`` is ``True`` , then Amazon Route 53 considers the health check to be unhealthy.

   

  Specify this value only if you want to change it.

  

``--health-threshold`` (integer)


  The minimum number of child health checks that must be healthy for Amazon Route 53 to consider the parent health check to be healthy. Valid values are integers between 0 and 256, inclusive.

   

  Specify this value only if you want to change it.

  

``--child-health-checks`` (list)


  For a specified parent health check, a list of ``health-check-id`` values for the associated child health checks.

   

  Specify this value only if you want to change it.

  



Syntax::

  "string" "string" ...



``--enable-sni`` | ``--no-enable-sni`` (boolean)


  Specify whether you want Amazon Route 53 to send the value of ``fully-qualified-domain-name`` to the endpoint in the ``client_hello`` message during TLS negotiation. If you don't specify a value for ``no-enable-sni`` , Amazon Route 53 defaults to ``true`` when ``Type`` is ``HTTPS`` or ``HTTPS_STR_MATCH`` and defaults to ``false`` when ``Type`` is any other value.

   

  Specify this value only if you want to change it.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

      

      port on which connection will be opened to the instance to health check. For HTTP and HTTP_STR_MATCH this defaults to 80 if the port is not specified. For HTTPS and HTTPS_STR_MATCH this defaults to 443 if the port is not specified.

      

      

    Type -> (string)

      

      The type of health check to be performed. Currently supported types are TCP, HTTP, HTTPS, HTTP_STR_MATCH, and HTTPS_STR_MATCH.

      

      

    ResourcePath -> (string)

      

      Path to ping on the instance to check the health. Required for HTTP, HTTPS, HTTP_STR_MATCH, and HTTPS_STR_MATCH health checks. The HTTP request is issued to the instance on the given port and path.

      

      

    FullyQualifiedDomainName -> (string)

      

      Fully qualified domain name of the instance to be health checked.

      

      

    SearchString -> (string)

      

      A string to search for in the body of a health check response. Required for HTTP_STR_MATCH and HTTPS_STR_MATCH health checks. Amazon Route 53 considers case when searching for ``search-string`` in the response body. 

      

      

    RequestInterval -> (integer)

      

      The number of seconds between the time that Amazon Route 53 gets a response from your endpoint and the time that it sends the next health-check request.

       

      Each Amazon Route 53 health checker makes requests at this interval. Valid values are 10 and 30. The default value is 30.

      

      

    FailureThreshold -> (integer)

      

      The number of consecutive health checks that an endpoint must pass or fail for Amazon Route 53 to change the current status of the endpoint from unhealthy to healthy or vice versa.

       

      Valid values are integers between 1 and 10. For more information, see "How Amazon Route 53 Determines Whether an Endpoint Is Healthy" in the Amazon Route 53 Developer Guide.

      

      

    MeasureLatency -> (boolean)

      

      A Boolean value that indicates whether you want Amazon Route 53 to measure the latency between health checkers in multiple AWS regions and your endpoint and to display CloudWatch latency graphs in the Amazon Route 53 console.

      

      

    Inverted -> (boolean)

      

      A boolean value that indicates whether the status of health check should be inverted. For example, if a health check is healthy but ``no-inverted`` is ``True`` , then Amazon Route 53 considers the health check to be unhealthy.

      

      

    HealthThreshold -> (integer)

      

      The minimum number of child health checks that must be healthy for Amazon Route 53 to consider the parent health check to be healthy. Valid values are integers between 0 and 256, inclusive.

      

      

    ChildHealthChecks -> (list)

      

      For a specified parent health check, a list of ``health-check-id`` values for the associated child health checks.

      

      (string)

        

        

      

    EnableSNI -> (boolean)

      

      Specify whether you want Amazon Route 53 to send the value of ``fully-qualified-domain-name`` to the endpoint in the ``client_hello`` message during TLS negotiation. If you don't specify a value for ``no-enable-sni`` , Amazon Route 53 defaults to ``true`` when ``Type`` is ``HTTPS`` or ``HTTPS_STR_MATCH`` and defaults to ``false`` when ``Type`` is any other value.

      

      

    

  HealthCheckVersion -> (long)

    

    The version of the health check. You can optionally pass this value in a call to ``update-health-check`` to prevent overwriting another change to the health check.

    

    

  

