[ :ref:`aws <cli:aws>` . :ref:`elasticache <cli:aws elasticache>` ]

.. _cli:aws elasticache describe-events:


***************
describe-events
***************



===========
Description
===========



Returns events related to cache clusters, cache security groups, and cache parameter groups. You can obtain events specific to a particular cache cluster, cache security group, or cache parameter group by providing the name as a parameter.

 

By default, only the events occurring within the last hour are returned; however, you can retrieve up to 14 days' worth of events if necessary.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticache-2015-02-02/DescribeEvents>`_


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
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--source-identifier`` (string)


  The identifier of the event source for which events are returned. If not specified, all sources are included in the response.

  

``--source-type`` (string)


  The event source to retrieve events for. If no value is specified, all events are returned.

  

  Possible values:

  
  *   ``cache-cluster``

  
  *   ``cache-parameter-group``

  
  *   ``cache-security-group``

  
  *   ``cache-subnet-group``

  
  *   ``replication-group``

  

  

``--start-time`` (timestamp)


  The beginning of the time interval to retrieve events for, specified in ISO 8601 format.

   

   **Example:** 2017-03-30T07:03:49.555Z

  

``--end-time`` (timestamp)


  The end of the time interval for which to retrieve events, specified in ISO 8601 format.

   

   **Example:** 2017-03-30T07:03:49.555Z

  

``--duration`` (integer)


  The number of minutes worth of events to retrieve.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

      

      

    

  

