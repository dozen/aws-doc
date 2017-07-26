[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds describe-event-categories:


*************************
describe-event-categories
*************************



===========
Description
===========



Displays a list of categories for all event source types, or, if specified, for a specified source type. You can see a list of the event categories and source types in the `Events`_ topic in the *Amazon RDS User Guide.* 



========
Synopsis
========

::

    describe-event-categories
  [--source-type <value>]
  [--filters <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

        

        

      

    

  



.. _Events: http://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_Events.html
