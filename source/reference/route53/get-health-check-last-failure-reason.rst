[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 get-health-check-last-failure-reason:


************************************
get-health-check-last-failure-reason
************************************



===========
Description
===========



Gets the reason that a specified health check failed most recently.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53-2013-04-01/GetHealthCheckLastFailureReason>`_


========
Synopsis
========

::

    get-health-check-last-failure-reason
  --health-check-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--health-check-id`` (string)


  The ID for the health check for which you want the last failure reason. When you created the health check, ``create-health-check`` returned the ID in the response, in the ``health-check-id`` element.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

HealthCheckObservations -> (list)

  

  A list that contains one ``Observation`` element for each Amazon Route 53 health checker that is reporting a last failure reason. 

  

  (structure)

    

    A complex type that contains the last failure reason as reported by one Amazon Route 53 health checker.

    

    Region -> (string)

      

      The region of the Amazon Route 53 health checker that provided the status in ``StatusReport`` .

      

      

    IPAddress -> (string)

      

      The IP address of the Amazon Route 53 health checker that provided the failure reason in ``StatusReport`` .

      

      

    StatusReport -> (structure)

      

      A complex type that contains the last failure reason as reported by one Amazon Route 53 health checker and the time of the failed health check.

      

      Status -> (string)

        

        A description of the status of the health check endpoint as reported by one of the Amazon Route 53 health checkers.

        

        

      CheckedTime -> (timestamp)

        

        The date and time that the health checker performed the health check in `ISO 8601 format <https://en.wikipedia.org/wiki/ISO_8601>`_ and Coordinated Universal Time (UTC). For example, the value ``2017-03-27T17:48:16.751Z`` represents March 27, 2017 at 17:48:16.751 UTC.

        

        

      

    

  

