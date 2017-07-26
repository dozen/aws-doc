[ :ref:`aws <cli:aws>` . :ref:`dms <cli:aws dms>` ]

.. _cli:aws dms describe-events:


***************
describe-events
***************



===========
Description
===========



Lists events for a given source identifier and source type. You can also specify a start and end time. For more information on AWS DMS events, see `Working with Events and Notifications <http://docs.aws.amazon.com/dms/latest/userguide/CHAP_Events.html>`_ . 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dms-2016-01-01/DescribeEvents>`_


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
  [--max-records <value>]
  [--marker <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--source-identifier`` (string)


  The identifier of the event source. An identifier must begin with a letter and must contain only ASCII letters, digits, and hyphens. It cannot end with a hyphen or contain two consecutive hyphens. 

  

``--source-type`` (string)


  The type of AWS DMS resource that generates events.

   

  Valid values: replication-instance | migration-task

  

  Possible values:

  
  *   ``replication-instance``

  

  

``--start-time`` (timestamp)


  The start time for the events to be listed.

  

``--end-time`` (timestamp)


  The end time for the events to be listed.

  

``--duration`` (integer)


  The duration of the events to be listed.

  

``--event-categories`` (list)


  A list of event categories for a source type that you want to subscribe to.

  



Syntax::

  "string" "string" ...



``--filters`` (list)


  Filters applied to the action.

  



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



``--max-records`` (integer)


  The maximum number of records to include in the response. If more records exist than the specified ``MaxRecords`` value, a pagination token called a marker is included in the response so that the remaining results can be retrieved. 

   

  Default: 100

   

  Constraints: Minimum 20, maximum 100.

  

``--marker`` (string)


  An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Marker -> (string)

  

  An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

  

  

Events -> (list)

  

  The events described.

  

  (structure)

    

    

    

    SourceIdentifier -> (string)

      

      The identifier of the event source. An identifier must begin with a letter and must contain only ASCII letters, digits, and hyphens; it cannot end with a hyphen or contain two consecutive hyphens. 

       

      Constraints:replication instance, endpoint, migration task

      

      

    SourceType -> (string)

      

      The type of AWS DMS resource that generates events. 

       

      Valid values: replication-instance | endpoint | migration-task

      

      

    Message -> (string)

      

      The event message.

      

      

    EventCategories -> (list)

      

      The event categories available for the specified source type.

      

      (string)

        

        

      

    Date -> (timestamp)

      

      The date of the event.

      

      

    

  

