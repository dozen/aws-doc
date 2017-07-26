[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 get-health-check-last-failure-reason:


************************************
get-health-check-last-failure-reason
************************************



===========
Description
===========



If you want to learn why a health check is currently failing or why it failed most recently (if at all), you can get the failure reason for the most recent failure. Send a ``GET`` request to the ``/*Route 53 API version* /healthcheck/*health check ID* /lastfailurereason`` resource.



========
Synopsis
========

::

    get-health-check-last-failure-reason
  --health-check-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--health-check-id`` (string)


  The ID of the health check for which you want to retrieve the reason for the most recent failure.

  

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

        

        

      

    

  

