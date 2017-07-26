[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift describe-events:


***************
describe-events
***************



===========
Description
===========



Returns events related to clusters, security groups, snapshots, and parameter groups for the past 14 days. Events specific to a particular cluster, security group, snapshot or parameter group can be obtained by providing the name as a parameter. By default, the past hour of events are returned.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/redshift-2012-12-01/DescribeEvents>`_


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


  The identifier of the event source for which events will be returned. If this parameter is not specified, then all sources are included in the response.

   

  Constraints:

   

  If *SourceIdentifier* is supplied, *source-type* must also be provided.

   

   
  * Specify a cluster identifier when *source-type* is ``cluster`` . 
   
  * Specify a cluster security group name when *source-type* is ``cluster-security-group`` . 
   
  * Specify a cluster parameter group name when *source-type* is ``cluster-parameter-group`` . 
   
  * Specify a cluster snapshot identifier when *source-type* is ``cluster-snapshot`` . 
   

  

``--source-type`` (string)


  The event source to retrieve events for. If no value is specified, all events are returned.

   

  Constraints:

   

  If *source-type* is supplied, *SourceIdentifier* must also be provided.

   

   
  * Specify ``cluster`` when *SourceIdentifier* is a cluster identifier. 
   
  * Specify ``cluster-security-group`` when *SourceIdentifier* is a cluster security group name. 
   
  * Specify ``cluster-parameter-group`` when *SourceIdentifier* is a cluster parameter group name. 
   
  * Specify ``cluster-snapshot`` when *SourceIdentifier* is a cluster snapshot identifier. 
   

  

  Possible values:

  
  *   ``cluster``

  
  *   ``cluster-parameter-group``

  
  *   ``cluster-security-group``

  
  *   ``cluster-snapshot``

  

  

``--start-time`` (timestamp)


  The beginning of the time interval to retrieve events for, specified in ISO 8601 format. For more information about ISO 8601, go to the `ISO8601 Wikipedia page. <http://en.wikipedia.org/wiki/ISO_8601>`_  

   

  Example: ``2009-07-08T18:00Z``  

  

``--end-time`` (timestamp)


  The end of the time interval for which to retrieve events, specified in ISO 8601 format. For more information about ISO 8601, go to the `ISO8601 Wikipedia page. <http://en.wikipedia.org/wiki/ISO_8601>`_  

   

  Example: ``2009-07-08T18:00Z``  

  

``--duration`` (integer)


  The number of minutes prior to the time of the request for which to retrieve events. For example, if the request is sent at 18:00 and you specify a duration of 60, then only events which have occurred after 17:00 will be returned.

   

  Default: ``60``  

  

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



========
Examples
========

Describe All Events
-------------------

this example returns all events. By default, the output is in JSON format.

Command::

   aws redshift describe-events

Result::

    {
       "Events": [
          {
          "Date": "2013-01-22T19:17:03.640Z",
          "SourceIdentifier": "myclusterparametergroup",
          "Message": "Cluster parameter group myclusterparametergroup has been created.",
          "SourceType": "cluster-parameter-group"
          } ],
       "ResponseMetadata": {
          "RequestId": "9f056111-64c9-11e2-9390-ff04f2c1e638"
       }
    }

You can also obtain the same information in text format using the ``--output text`` option.

Command::

   aws redshift describe-events --output text

Result::

    2013-01-22T19:17:03.640Z	myclusterparametergroup	Cluster parameter group myclusterparametergroup has been created.	cluster-parameter-group
    RESPONSEMETADATA	8e5fe765-64c9-11e2-bce3-e56f52c50e17




======
Output
======

Marker -> (string)

  

  A value that indicates the starting point for the next set of response records in a subsequent request. If a value is returned in a response, you can retrieve the next set of records by providing this returned marker value in the ``Marker`` parameter and retrying the command. If the ``Marker`` field is empty, all response records have been retrieved for the request. 

  

  

Events -> (list)

  

  A list of ``Event`` instances. 

  

  (structure)

    

    Describes an event.

    

    SourceIdentifier -> (string)

      

      The identifier for the source of the event.

      

      

    SourceType -> (string)

      

      The source type for this event.

      

      

    Message -> (string)

      

      The text of this event.

      

      

    EventCategories -> (list)

      

      A list of the event categories.

       

      Values: Configuration, Management, Monitoring, Security

      

      (string)

        

        

      

    Severity -> (string)

      

      The severity of the event.

       

      Values: ERROR, INFO

      

      

    Date -> (timestamp)

      

      The date and time of the event.

      

      

    EventId -> (string)

      

      The identifier of the event.

      

      

    

  

