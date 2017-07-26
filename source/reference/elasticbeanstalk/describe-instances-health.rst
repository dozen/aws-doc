[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk describe-instances-health:


*************************
describe-instances-health
*************************



===========
Description
===========



Returns more detailed information about the health of the specified instances (for example, CPU utilization, load average, and causes). The **describe-instances-health** operation is only available with AWS Elastic Beanstalk Enhanced Health.



========
Synopsis
========

::

    describe-instances-health
  [--environment-name <value>]
  [--environment-id <value>]
  [--attribute-names <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--environment-name`` (string)


  Specifies the AWS Elastic Beanstalk environment name.

  

``--environment-id`` (string)


  Specifies the AWS Elastic Beanstalk environment ID.

  

``--attribute-names`` (list)


  Specifies the response elements you wish to receive. If no attribute names are specified, AWS Elastic Beanstalk only returns a list of instances.

  



Syntax::

  "string" "string" ...

  Where valid values are:
    HealthStatus
    Color
    Causes
    ApplicationMetrics
    RefreshedAt
    LaunchedAt
    System
    All





``--next-token`` (string)


  Specifies the next token of the request.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To view environment health**

The following command retrieves health information for instances in an environment named ``my-env``::

  aws elasticbeanstalk describe-instances-health --environment-name my-env --attribute-names All

Output::

  {
      "InstanceHealthList": [
          {
              "InstanceId": "i-08691cc7",
              "ApplicationMetrics": {
                  "Duration": 10,
                  "Latency": {
                      "P99": 0.006,
                      "P75": 0.002,
                      "P90": 0.004,
                      "P95": 0.005,
                      "P85": 0.003,
                      "P10": 0.0,
                      "P999": 0.006,
                      "P50": 0.001
                  },
                  "RequestCount": 48,
                  "StatusCodes": {
                      "Status3xx": 0,
                      "Status2xx": 47,
                      "Status5xx": 0,
                      "Status4xx": 1
                  }
              },
              "System": {
                  "LoadAverage": [
                      0.0,
                      0.02,
                      0.05
                  ],
                  "CPUUtilization": {
                      "SoftIRQ": 0.1,
                      "IOWait": 0.2,
                      "System": 0.3,
                      "Idle": 97.8,
                      "User": 1.5,
                      "IRQ": 0.0,
                      "Nice": 0.1
                  }
              },
              "Color": "Green",
              "HealthStatus": "Ok",
              "LaunchedAt": "2015-08-13T19:17:09Z",
              "Causes": []
          }
      ],
      "RefreshedAt": "2015-08-20T21:09:08Z"
  }

Health information is only available for environments with enhanced health reporting enabled. For more information, see `Enhanced Health Reporting and Monitoring`_ in the *AWS Elastic Beanstalk Developer Guide*.

.. _`Enhanced Health Reporting and Monitoring`: http://integ-docs-aws.amazon.com/elasticbeanstalk/latest/dg/health-enhanced.html


======
Output
======

InstanceHealthList -> (list)

  

  Contains the response body with information about the health of the instance.

  

  (structure)

    

    Represents health information from the specified instance that belongs to the AWS Elastic Beanstalk environment. Use the ``InstanceId`` property to specify the application instance for which you'd like to return data.

    

    InstanceId -> (string)

      

      The ID of the Amazon EC2 instance.

      

      

    HealthStatus -> (string)

      

      Returns the health status of the specified instance. For more information, see `Health Colors and Statuses`_ .

      

      

    Color -> (string)

      

      Represents the color indicator that gives you information about the health of the EC2 instance. For more information, see `Health Colors and Statuses`_ .

      

      

    Causes -> (list)

      

      Represents the causes, which provide more information about the current health status.

      

      (string)

        

        

      

    LaunchedAt -> (timestamp)

      

      The time at which the EC2 instance was launched.

      

      

    ApplicationMetrics -> (structure)

      

      Represents the application metrics for a specified environment.

      

      Duration -> (integer)

        

        The amount of time that the metrics cover (usually 10 seconds). For example, you might have 5 requests (``request_count`` ) within the most recent time slice of 10 seconds (``duration`` ).

        

        

      RequestCount -> (integer)

        

        Average number of requests handled by the web server per second over the last 10 seconds.

        

        

      StatusCodes -> (structure)

        

        Represents the percentage of requests over the last 10 seconds that resulted in each type of status code response.

        

        Status2xx -> (integer)

          

          The percentage of requests over the last 10 seconds that resulted in a 2xx (200, 201, etc.) status code.

          

          

        Status3xx -> (integer)

          

          The percentage of requests over the last 10 seconds that resulted in a 3xx (300, 301, etc.) status code.

          

          

        Status4xx -> (integer)

          

          The percentage of requests over the last 10 seconds that resulted in a 4xx (400, 401, etc.) status code.

          

          

        Status5xx -> (integer)

          

          The percentage of requests over the last 10 seconds that resulted in a 5xx (500, 501, etc.) status code.

          

          

        

      Latency -> (structure)

        

        Represents the average latency for the slowest X percent of requests over the last 10 seconds. Latencies are in seconds with one milisecond resolution.

        

        P999 -> (double)

          

          The average latency for the slowest 0.1 percent of requests over the last 10 seconds.

          

          

        P99 -> (double)

          

          The average latency for the slowest 1 percent of requests over the last 10 seconds.

          

          

        P95 -> (double)

          

          The average latency for the slowest 5 percent of requests over the last 10 seconds.

          

          

        P90 -> (double)

          

          The average latency for the slowest 10 percent of requests over the last 10 seconds.

          

          

        P85 -> (double)

          

          The average latency for the slowest 15 percent of requests over the last 10 seconds.

          

          

        P75 -> (double)

          

          The average latency for the slowest 25 percent of requests over the last 10 seconds.

          

          

        P50 -> (double)

          

          The average latency for the slowest 50 percent of requests over the last 10 seconds.

          

          

        P10 -> (double)

          

          The average latency for the slowest 90 percent of requests over the last 10 seconds.

          

          

        

      

    System -> (structure)

      

      Represents CPU utilization and load average information for applications running in the specified environment.

      

      CPUUtilization -> (structure)

        

        Represents CPU utilization information from the specified instance that belongs to the AWS Elastic Beanstalk environment. Use the ``instanceId`` property to specify the application instance for which you'd like to return data.

        

        User -> (double)

          

          Percentage of time that the CPU has spent in the ``User`` state over the last 10 seconds.

          

          

        Nice -> (double)

          

          Percentage of time that the CPU has spent in the ``Nice`` state over the last 10 seconds.

          

          

        System -> (double)

          

          Percentage of time that the CPU has spent in the ``System`` state over the last 10 seconds.

          

          

        Idle -> (double)

          

          Percentage of time that the CPU has spent in the ``Idle`` state over the last 10 seconds.

          

          

        IOWait -> (double)

          

          Percentage of time that the CPU has spent in the ``I/O Wait`` state over the last 10 seconds.

          

          

        IRQ -> (double)

          

          Percentage of time that the CPU has spent in the ``IRQ`` state over the last 10 seconds.

          

          

        SoftIRQ -> (double)

          

          Percentage of time that the CPU has spent in the ``SoftIRQ`` state over the last 10 seconds.

          

          

        

      LoadAverage -> (list)

        

        Load average in the last 1-minute and 5-minute periods. For more information, see `Operating System Metrics`_ .

        

        (double)

          

          

        

      

    

  

RefreshedAt -> (timestamp)

  

  The date and time the information was last refreshed.

  

  

NextToken -> (string)

  

  The next token.

  

  



.. _Operating System Metrics: http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/health-enhanced-metrics.html#health-enhanced-metrics-os
.. _Health Colors and Statuses: http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/health-enhanced-status.html
