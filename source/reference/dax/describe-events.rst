[ :ref:`aws <cli:aws>` . :ref:`dax <cli:aws dax>` ]

.. _cli:aws dax describe-events:


***************
describe-events
***************



===========
Description
===========



Returns events related to DAX clusters and parameter groups. You can obtain events specific to a particular DAX cluster or parameter group by providing the name as a parameter.

 

By default, only the events occurring within the last hour are returned; however, you can retrieve up to 14 days' worth of events if necessary.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dax-2017-04-19/DescribeEvents>`_


========
Synopsis
========

::

    describe-events
  [--source-name <value>]
  [--source-type <value>]
  [--start-time <value>]
  [--end-time <value>]
  [--duration <value>]
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--source-name`` (string)


  The identifier of the event source for which events will be returned. If not specified, then all sources are included in the response.

  

``--source-type`` (string)


  The event source to retrieve events for. If no value is specified, all events are returned.

  

  Possible values:

  
  *   ``CLUSTER``

  
  *   ``PARAMETER_GROUP``

  
  *   ``SUBNET_GROUP``

  

  

``--start-time`` (timestamp)


  The beginning of the time interval to retrieve events for, specified in ISO 8601 format.

  

``--end-time`` (timestamp)


  The end of the time interval for which to retrieve events, specified in ISO 8601 format.

  

``--duration`` (integer)


  The number of minutes' worth of events to retrieve.

  

``--max-results`` (integer)


  The maximum number of results to include in the response. If more results exist than the specified ``MaxResults`` value, a token is included in the response so that the remaining results can be retrieved.

   

  The value for ``MaxResults`` must be between 20 and 100.

  

``--next-token`` (string)


  An optional token returned from a prior request. Use this token for pagination of results from this action. If this parameter is specified, the response includes only results beyond the token, up to the value specified by ``MaxResults`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

NextToken -> (string)

  

  Provides an identifier to allow retrieval of paginated results.

  

  

Events -> (list)

  

  An array of events. Each element in the array represents one event.

  

  (structure)

    

    Represents a single occurrence of something interesting within the system. Some examples of events are creating a DAX cluster, adding or removing a node, or rebooting a node.

    

    SourceName -> (string)

      

      The source of the event. For example, if the event occurred at the node level, the source would be the node ID.

      

      

    SourceType -> (string)

      

      Specifies the origin of this event - a cluster, a parameter group, a node ID, etc.

      

      

    Message -> (string)

      

      A user-defined message associated with the event.

      

      

    Date -> (timestamp)

      

      The date and time when the event occurred.

      

      

    

  

