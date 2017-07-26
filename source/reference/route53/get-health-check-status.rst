[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 get-health-check-status:


***********************
get-health-check-status
***********************



===========
Description
===========



To retrieve the health check status, send a ``GET`` request to the ``/*Route 53 API version* /healthcheck/*health check ID* /status`` resource. You can use this call to get a health check's current status. 



========
Synopsis
========

::

    get-health-check-status
  --health-check-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--health-check-id`` (string)


  If you want Amazon Route 53 to return this resource record set in response to a DNS query only when a health check is passing, include the ``health-check-id`` element and specify the ID of the applicable health check.

   

  Amazon Route 53 determines whether a resource record set is healthy by periodically sending a request to the endpoint that is specified in the health check. If that endpoint returns an HTTP status code of 2xx or 3xx, the endpoint is healthy. If the endpoint returns an HTTP status code of 400 or greater, or if the endpoint doesn't respond for a certain amount of time, Amazon Route 53 considers the endpoint unhealthy and also considers the resource record set unhealthy.

   

  The ``health-check-id`` element is only useful when Amazon Route 53 is choosing between two or more resource record sets to respond to a DNS query, and you want Amazon Route 53 to base the choice in part on the status of a health check. Configuring health checks only makes sense in the following configurations:

   

   
  * You're checking the health of the resource record sets in a weighted, latency, geolocation, or failover resource record set, and you specify health check IDs for all of the resource record sets. If the health check for one resource record set specifies an endpoint that is not healthy, Amazon Route 53 stops responding to queries using the value for that resource record set.
   
  * You set ``EvaluateTargetHealth`` to ``true`` for the resource record sets in an alias, weighted alias, latency alias, geolocation alias, or failover alias resource record set, and you specify health check IDs for all of the resource record sets that are referenced by the alias resource record sets. For more information about this configuration, see  EvaluateTargetHealth . Amazon Route 53 doesn't check the health of the endpoint specified in the resource record set, for example, the endpoint specified by the IP address in the ``Value`` element. When you add a ``health-check-id`` element to a resource record set, Amazon Route 53 checks the health of the endpoint that you specified in the health check. 
   

   

  For geolocation resource record sets, if an endpoint is unhealthy, Amazon Route 53 looks for a resource record set for the larger, associated geographic region. For example, suppose you have resource record sets for a state in the United States, for the United States, for North America, and for all locations. If the endpoint for the state resource record set is unhealthy, Amazon Route 53 checks the resource record sets for the United States, for North America, and for all locations (a resource record set for which the value of CountryCode is ``*`` ), in that order, until it finds a resource record set for which the endpoint is healthy.

   

  If your health checks specify the endpoint only by domain name, we recommend that you create a separate health check for each endpoint. For example, create a health check for each HTTP server that is serving content for www.example.com. For the value of ``FullyQualifiedDomainName`` , specify the domain name of the server (such as ``us-east-1-www.example.com`` ), not the name of the resource record sets (example.com).

   

  .. warning::

    In this configuration, if you create a health check for which the value of ``FullyQualifiedDomainName`` matches the name of the resource record sets and then associate the health check with those resource record sets, health check results will be unpredictable.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

HealthCheckObservations -> (list)

  

  A list that contains one ``HealthCheckObservation`` element for each Amazon Route 53 health checker.

  

  (structure)

    

    A complex type that contains the IP address of a Amazon Route 53 health checker and the reason for the health check status.

    

    IPAddress -> (string)

      

      The IP address of the Amazon Route 53 health checker that performed the health check.

      

      

    StatusReport -> (structure)

      

      A complex type that contains information about the health check status for the current observation.

      

      Status -> (string)

        

        The observed health check status.

        

        

      CheckedTime -> (timestamp)

        

        The date and time the health check status was observed, in the format ``YYYY-MM-DDThh:mm:ssZ`` , as specified in the ISO 8601 standard (for example, 2009-11-19T19:37:58Z). The ``Z`` after the time indicates that the time is listed in Coordinated Universal Time (UTC).

        

        

      

    

  

