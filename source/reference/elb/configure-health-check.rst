[ :ref:`aws <cli:aws>` . :ref:`elb <cli:aws elb>` ]

.. _cli:aws elb configure-health-check:


**********************
configure-health-check
**********************



===========
Description
===========



Specifies the health check settings to use when evaluating the health state of your back-end instances.

 

For more information, see `Configure Health Checks`_ in the *Elastic Load Balancing Developer Guide* .



========
Synopsis
========

::

    configure-health-check
  --load-balancer-name <value>
  --health-check <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--load-balancer-name`` (string)


  The name of the load balancer.

  

``--health-check`` (structure)


  The configuration information for the new health check.

  



Shorthand Syntax::

    Target=string,Interval=integer,Timeout=integer,UnhealthyThreshold=integer,HealthyThreshold=integer




JSON Syntax::

  {
    "Target": "string",
    "Interval": integer,
    "Timeout": integer,
    "UnhealthyThreshold": integer,
    "HealthyThreshold": integer
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To specify the health check settings for your backend EC2 instances**

This example specifies the health check settings used to evaluate the health of your backend EC2 instances.


Command::

    aws elb configure-health-check --load-balancer-name my-load-balancer --health-check Target=HTTP:80/png,Interval=30,UnhealthyThreshold=2,HealthyThreshold=2,Timeout=3

Output::

   {
      "HealthCheck": {
          "HealthyThreshold": 2,
          "Interval": 30,
          "Target": "HTTP:80/png",
          "Timeout": 3,
          "UnhealthyThreshold": 2
    }



======
Output
======

HealthCheck -> (structure)

  

  The updated health check.

  

  Target -> (string)

    

    The instance being checked. The protocol is either TCP, HTTP, HTTPS, or SSL. The range of valid ports is one (1) through 65535.

     

    TCP is the default, specified as a TCP: port pair, for example "TCP:5000". In this case, a health check simply attempts to open a TCP connection to the instance on the specified port. Failure to connect within the configured timeout is considered unhealthy.

     

    SSL is also specified as SSL: port pair, for example, SSL:5000.

     

    For HTTP/HTTPS, you must include a ping path in the string. HTTP is specified as a HTTP:port;/;PathToPing; grouping, for example "HTTP:80/weather/us/wa/seattle". In this case, a HTTP GET request is issued to the instance on the given port and path. Any answer other than "200 OK" within the timeout period is considered unhealthy.

     

    The total length of the HTTP ping target must be 1024 16-bit Unicode characters or less.

    

    

  Interval -> (integer)

    

    The approximate interval, in seconds, between health checks of an individual instance.

    

    

  Timeout -> (integer)

    

    The amount of time, in seconds, during which no response means a failed health check.

     

    This value must be less than the ``Interval`` value.

    

    

  UnhealthyThreshold -> (integer)

    

    The number of consecutive health check failures required before moving the instance to the ``Unhealthy`` state.

    

    

  HealthyThreshold -> (integer)

    

    The number of consecutive health checks successes required before moving the instance to the ``Healthy`` state.

    

    

  



.. _Configure Health Checks: http://docs.aws.amazon.com/ElasticLoadBalancing/latest/DeveloperGuide/elb-healthchecks.html
