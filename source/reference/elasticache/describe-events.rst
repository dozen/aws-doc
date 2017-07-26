[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache describe-events:


***************
describe-events
***************



===========
Description
===========



The *describe-events* action returns events related to cache clusters, cache security groups, and cache parameter groups. You can obtain events specific to a particular cache cluster, cache security group, or cache parameter group by providing the name as a parameter.

 

By default, only the events occurring within the last hour are returned; however, you can retrieve up to 14 days' worth of events if necessary.



``describe-events`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Events``


========
Synopsis
========

::

    describe-events
  [--source-identifier <value>]
  [--source-type <value>]
  [--start-time <value>]
  [--end-time <value>]
  [--duration <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--source-identifier`` (string)


  The identifier of the event source for which events will be returned. If not specified, then all sources are included in the response.

  

``--source-type`` (string)


  The event source to retrieve events for. If no value is specified, all events are returned.

   

  Valid values are: ``cache-cluster`` | ``cache-parameter-group`` | ``cache-security-group`` | ``cache-subnet-group`` 

  

  Possible values:

  
  *   ``cache-cluster``

  
  *   ``cache-parameter-group``

  
  *   ``cache-security-group``

  
  *   ``cache-subnet-group``

  

  

``--start-time`` (timestamp)


  The beginning of the time interval to retrieve events for, specified in ISO 8601 format.

  

``--end-time`` (timestamp)


  The end of the time interval for which to retrieve events, specified in ISO 8601 format.

  

``--duration`` (integer)


  The number of minutes' worth of events to retrieve.

  

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



======
Output
======

Marker -> (string)

  

  Provides an identifier to allow retrieval of paginated results.

  

  

Events -> (list)

  

  A list of events. Each element in the list contains detailed information about one event.

  

  (structure)

    

    Represents a single occurrence of something interesting within the system. Some examples of events are creating a cache cluster, adding or removing a cache node, or rebooting a node.

    

    SourceIdentifier -> (string)

      

      The identifier for the source of the event. For example, if the event occurred at the cache cluster level, the identifier would be the name of the cache cluster.

      

      

    SourceType -> (string)

      

      Specifies the origin of this event - a cache cluster, a parameter group, a security group, etc.

      

      

    Message -> (string)

      

      The text of the event.

      

      

    Date -> (timestamp)

      

      The date and time when the event occurred.

      

      

    

  

