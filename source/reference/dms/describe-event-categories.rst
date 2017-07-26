[ :ref:`aws <cli:aws>` . :ref:`dms <cli:aws dms>` ]

.. _cli:aws dms describe-event-categories:


*************************
describe-event-categories
*************************



===========
Description
===========



Lists categories for all event source types, or, if specified, for a specified source type. You can see a list of the event categories and source types in `Working with Events and Notifications <http://docs.aws.amazon.com/dms/latest/userguide/CHAP_Events.html>`_ in the AWS Database Migration Service User Guide. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dms-2016-01-01/DescribeEventCategories>`_


========
Synopsis
========

::

    describe-event-categories
  [--source-type <value>]
  [--filters <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--source-type`` (string)


  The type of AWS DMS resource that generates events. 

   

  Valid values: replication-instance | migration-task

  

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



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

EventCategoryGroupList -> (list)

  

  A list of event categories.

  

  (structure)

    

    

    

    SourceType -> (string)

      

      The type of AWS DMS resource that generates events. 

       

      Valid values: replication-instance | replication-server | security-group | migration-task

      

      

    EventCategories -> (list)

      

      A list of event categories for a ``SourceType`` that you want to subscribe to. 

      

      (string)

        

        

      

    

  

