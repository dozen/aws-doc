[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 list-health-checks:


******************
list-health-checks
******************



===========
Description
===========



To retrieve a list of your health checks, send a ``GET`` request to the ``/*Route 53 API version* /healthcheck`` resource. The response to this request includes a ``HealthChecks`` element with zero, one, or multiple ``HealthCheck`` child elements. By default, the list of health checks is displayed on a single page. You can control the length of the page that is displayed by using the ``MaxItems`` parameter. You can use the ``Marker`` parameter to control the health check that the list begins with. 

 

.. note::

  Amazon Route 53 returns a maximum of 100 items. If you set MaxItems to a value greater than 100, Amazon Route 53 returns only the first 100.



``list-health-checks`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``HealthChecks``


========
Synopsis
========

::

    list-health-checks
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
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (string)
 

  The size of each page.

   

  

  

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To list the health checks associated with the current AWS account**

The following ``list-health-checks`` command lists detailed information about the first 100 health checks that are associated with the current AWS account.::

  aws route53 list-health-checks

If you have more than 100 health checks, or if you want to list them in groups smaller than 100, include the ``--maxitems`` parameter. For example, to list health checks one at a time, use the following command::

  aws route53 list-health-checks --max-items 1

To view the next health check, take the value of ``NextToken`` from the response to the previous command, and include it in the ``--starting-token`` parameter, for example::

  aws route53 list-health-checks --max-items 1 --starting-token 02ec8401-9879-4259-91fa-094674111111




======
Output
======

HealthChecks -> (list)

  

  A complex type that contains information about the health checks associated with the current AWS account.

  

  (structure)

    

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

      

      

    

  

Marker -> (string)

  

  If the request returned more than one page of results, submit another request and specify the value of ``NextMarker`` from the last response in the ``marker`` parameter to get the next page of results.

  

  

IsTruncated -> (boolean)

  

  A flag indicating whether there are more health checks to be listed. If your results were truncated, you can make a follow-up request for the next page of results by using the ``Marker`` element.

   

  Valid Values: ``true`` | ``false`` 

  

  

NextMarker -> (string)

  

  Indicates where to continue listing health checks. If  ListHealthChecksResponse$IsTruncated is ``true`` , make another request to ``list-health-checks`` and include the value of the ``NextMarker`` element in the ``Marker`` element to get the next page of results.

  

  

MaxItems -> (string)

  

  The maximum number of health checks to be included in the response body. If the number of health checks associated with this AWS account exceeds ``MaxItems`` , the value of  ListHealthChecksResponse$IsTruncated in the response is ``true`` . Call ``list-health-checks`` again and specify the value of  ListHealthChecksResponse$NextMarker in the  ListHostedZonesRequest$Marker element to get the next page of results.

  

  

