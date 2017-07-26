[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds describe-event-categories:


*************************
describe-event-categories
*************************



===========
Description
===========



Displays a list of categories for all event source types, or, if specified, for a specified source type. You can see a list of the event categories and source types in the `Events <http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_Events.html>`_ topic in the *Amazon RDS User Guide.*  



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/DescribeEventCategories>`_


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


  The type of source that will be generating the events.

   

  Valid values: db-instance | db-parameter-group | db-security-group | db-snapshot

  

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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

EventCategoriesMapList -> (list)

  

  A list of EventCategoriesMap data types.

  

  (structure)

    

    Contains the results of a successful invocation of the  describe-event-categories action.

    

    SourceType -> (string)

      

      The source type that the returned categories belong to

      

      

    EventCategories -> (list)

      

      The event categories for the specified source type

      

      (string)

        

        

      

    

  

