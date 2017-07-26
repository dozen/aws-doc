[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds describe-events:


***************
describe-events
***************



===========
Description
===========



Returns events related to DB instances, DB security groups, DB snapshots, and DB parameter groups for the past 14 days. Events specific to a particular DB instance, DB security group, database snapshot, or DB parameter group can be obtained by providing the name as a parameter. By default, the past hour of events are returned. 



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
  [--generate-cli-skeleton]




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


  The beginning of the time interval to retrieve events for, specified in ISO 8601 format. For more information about ISO 8601, go to the `ISO8601 Wikipedia page.`_ 

   

  Example: 2009-07-08T18:00Z

  

``--end-time`` (timestamp)


  The end of the time interval for which to retrieve events, specified in ISO 8601 format. For more information about ISO 8601, go to the `ISO8601 Wikipedia page.`_ 

   

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

      

      

    

  



.. _ISO8601 Wikipedia page.: http://en.wikipedia.org/wiki/ISO_8601
