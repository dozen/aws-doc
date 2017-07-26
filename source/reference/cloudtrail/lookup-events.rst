[ :ref:`aws <cli:aws>` . :ref:`cloudtrail <cli:aws cloudtrail>` ]

.. _cli:aws cloudtrail lookup-events:


*************
lookup-events
*************



===========
Description
===========



Looks up API activity events captured by CloudTrail that create, update, or delete resources in your account. Events for a region can be looked up for the times in which you had CloudTrail turned on in that region during the last seven days. Lookup supports five different attributes: time range (defined by a start time and end time), user name, event name, resource type, and resource name. All attributes are optional. The maximum number of attributes that can be specified in any one lookup request are time range and one other attribute. The default number of results returned is 10, with a maximum of 50 possible. The response includes a token that you can use to get the next page of results. 

 

.. warning::

  The rate of lookup requests is limited to one per second per account. If this limit is exceeded, a throttling error occurs. 

 

.. warning::

  Events that occurred during the selected time range will not be available for lookup if CloudTrail logging was not enabled when the events occurred.



========
Synopsis
========

::

    lookup-events
  [--lookup-attributes <value>]
  [--start-time <value>]
  [--end-time <value>]
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




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
      "AttributeKey": "EventId"|"EventName"|"Username"|"ResourceType"|"ResourceName",
      "AttributeValue": "string"
    }
    ...
  ]



``--start-time`` (timestamp)


  Specifies that only events that occur after or at the specified time are returned. If the specified start time is after the specified end time, an error is returned.

  

``--end-time`` (timestamp)


  Specifies that only events that occur before or at the specified time are returned. If the specified end time is before the specified start time, an error is returned.

  

``--max-results`` (integer)


  The number of events to return. Possible values are 1 through 50. The default is 10.

  

``--next-token`` (string)


  The token to use to get the next page of results after a previous API call. This token must be passed in with the same parameters that were specified in the the original call. For example, if the original call specified an AttributeKey of 'Username' with a value of 'root', the call with next-token should include those same parameters.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

      

      

    Username -> (string)

      

      A user name or role name of the requester that called the API in the event returned.

      

      

    Resources -> (list)

      

      A list of resources referenced by the event returned.

      

      (structure)

        

        Specifies the type and name of a resource referenced by an event.

        

        ResourceType -> (string)

          

          The type of a resource referenced by the event returned. When the resource type cannot be determined, null is returned. Some examples of resource types are: **Instance** for EC2, **Trail** for CloudTrail, **DBInstance** for RDS, and **AccessKey** for IAM. For a list of resource types supported for event lookup, see `Resource Types Supported for Event Lookup`_ .

          

          

        ResourceName -> (string)

          

          The name of the resource referenced by the event returned. These are user-created names whose values will depend on the environment. For example, the resource name might be "auto-scaling-test-group" for an Auto Scaling Group or "i-1234567" for an EC2 Instance.

          

          

        

      

    CloudTrailEvent -> (string)

      

      A JSON string that contains a representation of the event returned.

      

      

    

  

NextToken -> (string)

  

  The token to use to get the next page of results after a previous API call. If the token does not appear, there are no more results to return. The token must be passed in with the same parameters as the previous call. For example, if the original call specified an AttributeKey of 'Username' with a value of 'root', the call with next-token should include those same parameters.

  

  



.. _Resource Types Supported for Event Lookup: http://docs.aws.amazon.com/awscloudtrail/latest/userguide/lookup_supported_resourcetypes.html
