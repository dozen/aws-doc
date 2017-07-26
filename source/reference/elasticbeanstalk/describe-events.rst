[ :ref:`aws <cli:aws>` . :ref:`elasticbeanstalk <cli:aws elasticbeanstalk>` ]

.. _cli:aws elasticbeanstalk describe-events:


***************
describe-events
***************



===========
Description
===========



Returns list of event descriptions matching criteria up to the last 6 weeks.

 

.. note::

  This action returns the most recent 1,000 events from the specified ``NextToken`` . 



``describe-events`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Events``


========
Synopsis
========

::

    describe-events
  [--application-name <value>]
  [--version-label <value>]
  [--template-name <value>]
  [--environment-id <value>]
  [--environment-name <value>]
  [--request-id <value>]
  [--severity <value>]
  [--start-time <value>]
  [--end-time <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--application-name`` (string)


  If specified, AWS Elastic Beanstalk restricts the returned descriptions to include only those associated with this application. 

  

``--version-label`` (string)


  If specified, AWS Elastic Beanstalk restricts the returned descriptions to those associated with this application version. 

  

``--template-name`` (string)


  If specified, AWS Elastic Beanstalk restricts the returned descriptions to those that are associated with this environment configuration. 

  

``--environment-id`` (string)


  If specified, AWS Elastic Beanstalk restricts the returned descriptions to those associated with this environment. 

  

``--environment-name`` (string)


  If specified, AWS Elastic Beanstalk restricts the returned descriptions to those associated with this environment. 

  

``--request-id`` (string)


  If specified, AWS Elastic Beanstalk restricts the described events to include only those associated with this request ID. 

  

``--severity`` (string)


  If specified, limits the events returned from this call to include only those with the specified severity or higher. 

  

  Possible values:

  
  *   ``TRACE``

  
  *   ``DEBUG``

  
  *   ``INFO``

  
  *   ``WARN``

  
  *   ``ERROR``

  
  *   ``FATAL``

  

  

``--start-time`` (timestamp)


  If specified, AWS Elastic Beanstalk restricts the returned descriptions to those that occur on or after this time. 

  

``--end-time`` (timestamp)


  If specified, AWS Elastic Beanstalk restricts the returned descriptions to those that occur up to, but not including, the ``EndTime`` . 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To view events for an environment**

The following command retrieves events for an environment named ``my-env``::

  aws elasticbeanstalk describe-events --environment-name my-env

Output (abbreviated)::

  {
      "Events": [
          {
              "ApplicationName": "my-app",
              "EnvironmentName": "my-env",
              "Message": "Environment health has transitioned from Info to Ok.",
              "EventDate": "2015-08-20T07:06:53.535Z",
              "Severity": "INFO"
          },
          {
              "ApplicationName": "my-app",
              "EnvironmentName": "my-env",
              "Severity": "INFO",
              "RequestId": "b7f3960b-4709-11e5-ba1e-07e16200da41",
              "Message": "Environment update completed successfully.",
              "EventDate": "2015-08-20T07:06:02.049Z"
          },
          ...
          {
              "ApplicationName": "my-app",
              "EnvironmentName": "my-env",
              "Severity": "INFO",
              "RequestId": "ca8dfbf6-41ef-11e5-988b-651aa638f46b",
              "Message": "Using elasticbeanstalk-us-west-2-012445113685 as Amazon S3 storage bucket for environment data.",
              "EventDate": "2015-08-13T19:16:27.561Z"
          },
          {
              "ApplicationName": "my-app",
              "EnvironmentName": "my-env",
              "Severity": "INFO",
              "RequestId": "cdfba8f6-41ef-11e5-988b-65638f41aa6b",
              "Message": "createEnvironment is starting.",
              "EventDate": "2015-08-13T19:16:26.581Z"
          }
      ]
  }


======
Output
======

Events -> (list)

  

  A list of  EventDescription . 

  

  (structure)

    

    Describes an event.

    

    EventDate -> (timestamp)

      

      The date when the event occurred.

      

      

    Message -> (string)

      

      The event message.

      

      

    ApplicationName -> (string)

      

      The application associated with the event.

      

      

    VersionLabel -> (string)

      

      The release label for the application version associated with this event.

      

      

    TemplateName -> (string)

      

      The name of the configuration associated with this event.

      

      

    EnvironmentName -> (string)

      

      The name of the environment associated with this event.

      

      

    RequestId -> (string)

      

      The web service request ID for the activity of this event.

      

      

    Severity -> (string)

      

      The severity level of this event. 

      

      

    

  

NextToken -> (string)

  

  If returned, this indicates that there are more results to obtain. Use this token in the next  describe-events call to get the next batch of events. 

  

  

