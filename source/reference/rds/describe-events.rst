[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds describe-events:


***************
describe-events
***************



===========
Description
===========



Returns events related to DB instances, DB security groups, DB snapshots, and DB parameter groups for the past 14 days. Events specific to a particular DB instance, DB security group, database snapshot, or DB parameter group can be obtained by providing the name as a parameter. By default, the past hour of events are returned.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/DescribeEvents>`_


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
  [--event-categories <value>]
  [--filters <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--source-identifier`` (string)


  The identifier of the event source for which events will be returned. If not specified, then all sources are included in the response.

   

  Constraints:

   

   
  * If SourceIdentifier is supplied, source-type must also be provided. 
   
  * If the source type is ``DBInstance`` , then a ``DBInstanceIdentifier`` must be supplied. 
   
  * If the source type is ``DBSecurityGroup`` , a ``DBSecurityGroupName`` must be supplied. 
   
  * If the source type is ``DBParameterGroup`` , a ``DBParameterGroupName`` must be supplied. 
   
  * If the source type is ``DBSnapshot`` , a ``DBSnapshotIdentifier`` must be supplied. 
   
  * Cannot end with a hyphen or contain two consecutive hyphens. 
   

  

``--source-type`` (string)


  The event source to retrieve events for. If no value is specified, all events are returned.

  

  Possible values:

  
  *   ``db-instance``

  
  *   ``db-parameter-group``

  
  *   ``db-security-group``

  
  *   ``db-snapshot``

  
  *   ``db-cluster``

  
  *   ``db-cluster-snapshot``

  

  

``--start-time`` (timestamp)


  The beginning of the time interval to retrieve events for, specified in ISO 8601 format. For more information about ISO 8601, go to the `ISO8601 Wikipedia page. <http://en.wikipedia.org/wiki/ISO_8601>`_  

   

  Example: 2009-07-08T18:00Z

  

``--end-time`` (timestamp)


  The end of the time interval for which to retrieve events, specified in ISO 8601 format. For more information about ISO 8601, go to the `ISO8601 Wikipedia page. <http://en.wikipedia.org/wiki/ISO_8601>`_  

   

  Example: 2009-07-08T18:00Z

  

``--duration`` (integer)


  The number of minutes to retrieve events for.

   

  Default: 60

  

``--event-categories`` (list)


  A list of event categories that trigger notifications for a event notification subscription.

  



Syntax::

  "string" "string" ...



``--filters`` (list)


  This parameter is not currently supported.

  



Shorthand Syntax::

    Name=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Values": ["string", ...]
    }
    ...
  ]



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

  

  An optional pagination token provided by a previous Events request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

  

  

Events -> (list)

  

  A list of  Event instances. 

  

  (structure)

    

    This data type is used as a response element in the  describe-events action. 

    

    SourceIdentifier -> (string)

      

      Provides the identifier for the source of the event.

      

      

    SourceType -> (string)

      

      Specifies the source type for this event.

      

      

    Message -> (string)

      

      Provides the text of this event.

      

      

    EventCategories -> (list)

      

      Specifies the category for the event.

      

      (string)

        

        

      

    Date -> (timestamp)

      

      Specifies the date and time of the event.

      

      

    SourceArn -> (string)

      

      The Amazon Resource Name (ARN) for the event.

      

      

    

  

