[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk describe-environment-health:


***************************
describe-environment-health
***************************



===========
Description
===========



Returns information about the overall health of the specified environment. The **describe-environment-health** operation is only available with AWS Elastic Beanstalk Enhanced Health.



========
Synopsis
========

::

    describe-environment-health
  [--environment-name <value>]
  [--environment-id <value>]
  [--attribute-names <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--environment-name`` (string)


  Specifies the AWS Elastic Beanstalk environment name.

   

  Condition: You must specify either this or an EnvironmentId, or both. If you do not specify either, AWS Elastic Beanstalk returns ``MissingRequiredParameter`` error. 

  

``--environment-id`` (string)


  Specifies the AWS Elastic Beanstalk environment ID.

   

  Condition: You must specify either this or an EnvironmentName, or both. If you do not specify either, AWS Elastic Beanstalk returns ``MissingRequiredParameter`` error. 

  

``--attribute-names`` (list)


  Specifies the response elements you wish to receive. If no attribute names are specified, AWS Elastic Beanstalk only returns the name of the environment.

  



Syntax::

  "string" "string" ...

  Where valid values are:
    Status
    Color
    Causes
    ApplicationMetrics
    InstancesHealth
    All
    HealthStatus
    RefreshedAt





``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To view environment health**

The following command retrieves overall health information for an environment named ``my-env``::

  aws elasticbeanstalk describe-environment-health --environment-name my-env --attribute-names All

Output::

  {
      "Status": "Ready",
      "EnvironmentName": "my-env",
      "Color": "Green",
      "ApplicationMetrics": {
          "Duration": 10,
          "Latency": {
              "P99": 0.004,
              "P75": 0.002,
              "P90": 0.003,
              "P95": 0.004,
              "P85": 0.003,
              "P10": 0.001,
              "P999": 0.004,
              "P50": 0.001
          },
          "RequestCount": 45,
          "StatusCodes": {
              "Status3xx": 0,
              "Status2xx": 45,
              "Status5xx": 0,
              "Status4xx": 0
          }
      },
      "RefreshedAt": "2015-08-20T21:09:18Z",
      "HealthStatus": "Ok",
      "InstancesHealth": {
          "Info": 0,
          "Ok": 1,
          "Unknown": 0,
          "Severe": 0,
          "Warning": 0,
          "Degraded": 0,
          "NoData": 0,
          "Pending": 0
      },
      "Causes": []
  }

Health information is only available for environments with enhanced health reporting enabled. For more information, see `Enhanced Health Reporting and Monitoring`_ in the *AWS Elastic Beanstalk Developer Guide*.

.. _`Enhanced Health Reporting and Monitoring`: http://integ-docs-aws.amazon.com/elasticbeanstalk/latest/dg/health-enhanced.html


======
Output
======

EnvironmentName -> (string)

  

  The AWS Elastic Beanstalk environment name.

  

  

HealthStatus -> (string)

  

  Contains the response body with information about the health of the environment.

  

  

Status -> (string)

  

  Returns the health status value of the environment. For more information, see `Health Colors and Statuses`_ .

  

  

Color -> (string)

  

  Returns the color indicator that tells you information about the health of the environment. For more information, see `Health Colors and Statuses`_ .

  

  

Causes -> (list)

  

  Returns potential causes for the reported status.

  

  (string)

    

    

  

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

      

      

    

  

InstancesHealth -> (structure)

  

  Represents summary information about the health of an instance. For more information, see `Health Colors and Statuses`_ .

  

  NoData -> (integer)

    

    **Grey.** AWS Elastic Beanstalk and the health agent are reporting no data on an instance.

    

    

  Unknown -> (integer)

    

    **Grey.** AWS Elastic Beanstalk and the health agent are reporting an insufficient amount of data on an instance.

    

    

  Pending -> (integer)

    

    **Grey.** An operation is in progress on an instance within the command timeout.

    

    

  Ok -> (integer)

    

    **Green.** An instance is passing health checks and the health agent is not reporting any problems.

    

    

  Info -> (integer)

    

    **Green.** An operation is in progress on an instance.

    

    

  Warning -> (integer)

    

    **Yellow.** The health agent is reporting a moderate number of request failures or other issues for an instance or environment.

    

    

  Degraded -> (integer)

    

    **Red.** The health agent is reporting a high number of request failures or other issues for an instance or environment.

    

    

  Severe -> (integer)

    

    **Red.** The health agent is reporting a very high number of request failures or other issues for an instance or environment.

    

    

  

RefreshedAt -> (timestamp)

  

  The date and time the information was last refreshed.

  

  



.. _Health Colors and Statuses: http://docs.aws.amazon.com/elasticbeanstalk/latest/dg/health-enhanced-status.html
