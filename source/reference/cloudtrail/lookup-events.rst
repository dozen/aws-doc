[ :ref:`aws <cli:aws>` . :ref:`cloudtrail <cli:aws cloudtrail>` ]

.. _cli:aws cloudtrail lookup-events:


*************
lookup-events
*************



===========
Description
===========



Looks up API activity events captured by CloudTrail that create, update, or delete resources in your account. Events for a region can be looked up for the times in which you had CloudTrail turned on in that region during the last seven days. Lookup supports the following attributes:

 

 
* Event ID 
 
* Event name 
 
* Event source 
 
* Resource name 
 
* Resource type 
 
* User name 
 

 

All attributes are optional. The default number of results returned is 10, with a maximum of 50 possible. The response includes a token that you can use to get the next page of results.

 

.. warning::

   

  The rate of lookup requests is limited to one per second per account. If this limit is exceeded, a throttling error occurs.

   

 

.. warning::

   

  Events that occurred during the selected time range will not be available for lookup if CloudTrail logging was not enabled when the events occurred.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudtrail-2013-11-01/LookupEvents>`_


``lookup-events`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Events``


========
Synopsis
========

::

    lookup-events
  [--lookup-attributes <value>]
  [--start-time <value>]
  [--end-time <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--lookup-attributes`` (list)


  Contains a list of lookup attributes. Currently the list can contain only one item.

  



Shorthand Syntax::

    AttributeKey=string,AttributeValue=string ...




JSON Syntax::

  [
    {
      "AttributeKey": "EventId"|"EventName"|"Username"|"ResourceType"|"ResourceName"|"EventSource",
      "AttributeValue": "string"
    }
    ...
  ]



``--start-time`` (timestamp)


  Specifies that only events that occur after or at the specified time are returned. If the specified start time is after the specified end time, an error is returned.

  

``--end-time`` (timestamp)


  Specifies that only events that occur before or at the specified time are returned. If the specified end time is before the specified start time, an error is returned.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``next-token`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``next-token`` is provided in the command's output. To resume pagination, provide the ``next-token`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``next-token`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To look up events for a trail**

The following ``lookup-events`` command looks up API activity events by the attribute ``EventName``::

  aws cloudtrail lookup-events --lookup-attributes AttributeKey=EventName,AttributeValue=ConsoleLogin

Output::

  {
    "Events": [
       {
           "EventId": "654ccbc0-ba0d-486a-9076-dbf7274677a7", 
           "Username": "my-session-name", 
           "EventTime": 1453844532.0, 
           "CloudTrailEvent": "{\"eventVersion\":\"1.02\",\"userIdentity\":{\"type\":\"AssumedRole\",\"principalId\":\"AROAJIKPFTA72SWU4L7T4:my-session-name\",\"arn\":\"arn:aws:sts::123456789012:assumed-role/my-role/my-session-name\",\"accountId\":\"123456789012\",\"sessionContext\":{\"attributes\":{\"mfaAuthenticated\":\"false\",\"creationDate\":\"2016-01-26T21:42:12Z\"},\"sessionIssuer\":{\"type\":\"Role\",\"principalId\":\"AROAJIKPFTA72SWU4L7T4\",\"arn\":\"arn:aws:iam::123456789012:role/my-role\",\"accountId\":\"123456789012\",\"userName\":\"my-role\"}}},\"eventTime\":\"2016-01-26T21:42:12Z\",\"eventSource\":\"signin.amazonaws.com\",\"eventName\":\"ConsoleLogin\",\"awsRegion\":\"us-east-1\",\"sourceIPAddress\":\"72.21.198.70\",\"userAgent\":\"Mozilla/5.0 (Macintosh; Intel Mac OS X 10_9_5) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/47.0.2526.111 Safari/537.36\",\"requestParameters\":null,\"responseElements\":{\"ConsoleLogin\":\"Success\"},\"additionalEventData\":{\"MobileVersion\":\"No\",\"MFAUsed\":\"No\"},\"eventID\":\"654ccbc0-ba0d-486a-9076-dbf7274677a7\",\"eventType\":\"AwsConsoleSignIn\",\"recipientAccountId\":\"123456789012\"}", 
           "EventName": "ConsoleLogin", 
           "Resources": []
       }
    ]
  }

======
Output
======

Events -> (list)

  

  A list of events returned based on the lookup attributes specified and the CloudTrail event. The events list is sorted by time. The most recent event is listed first.

  

  (structure)

    

    Contains information about an event that was returned by a lookup request. The result includes a representation of a CloudTrail event.

    

    EventId -> (string)

      

      The CloudTrail ID of the event returned.

      

      

    EventName -> (string)

      

      The name of the event returned.

      

      

    EventTime -> (timestamp)

      

      The date and time of the event returned.

      

      

    EventSource -> (string)

      

      The AWS service that the request was made to.

      

      

    Username -> (string)

      

      A user name or role name of the requester that called the API in the event returned.

      

      

    Resources -> (list)

      

      A list of resources referenced by the event returned.

      

      (structure)

        

        Specifies the type and name of a resource referenced by an event.

        

        ResourceType -> (string)

          

          The type of a resource referenced by the event returned. When the resource type cannot be determined, null is returned. Some examples of resource types are: **Instance** for EC2, **Trail** for CloudTrail, **DBInstance** for RDS, and **AccessKey** for IAM. For a list of resource types supported for event lookup, see `Resource Types Supported for Event Lookup <http://docs.aws.amazon.com/awscloudtrail/latest/userguide/lookup_supported_resourcetypes.html>`_ .

          

          

        ResourceName -> (string)

          

          The name of the resource referenced by the event returned. These are user-created names whose values will depend on the environment. For example, the resource name might be "auto-scaling-test-group" for an Auto Scaling Group or "i-1234567" for an EC2 Instance.

          

          

        

      

    CloudTrailEvent -> (string)

      

      A JSON string that contains a representation of the event returned.

      

      

    

  

NextToken -> (string)

  

  The token to use to get the next page of results after a previous API call. If the token does not appear, there are no more results to return. The token must be passed in with the same parameters as the previous call. For example, if the original call specified an AttributeKey of 'Username' with a value of 'root', the call with next-token should include those same parameters.

  

  

