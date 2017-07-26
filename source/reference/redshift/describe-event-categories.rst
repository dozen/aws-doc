[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift describe-event-categories:


*************************
describe-event-categories
*************************



===========
Description
===========



Displays a list of event categories for all event source types, or for a specified source type. For a list of the event categories and source types, go to `Amazon Redshift Event Notifications`_ .



========
Synopsis
========

::

    describe-event-categories
  [--source-type <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--source-type`` (string)


  The source type, such as cluster or parameter group, to which the described event categories apply. 

   

  Valid values: cluster, snapshot, parameter group, and security group. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

EventCategoriesMapList -> (list)

  

  A list of event categories descriptions. 

  

  (structure)

    

    SourceType -> (string)

      

      The Amazon Redshift source type, such as cluster or cluster-snapshot, that the returned categories belong to.

      

      

    Events -> (list)

      

      The events in the event category.

      

      (structure)

        

        EventId -> (string)

          

          The identifier of an Amazon Redshift event.

          

          

        EventCategories -> (list)

          

          The category of an Amazon Redshift event.

          

          (string)

            

            

          

        EventDescription -> (string)

          

          The description of an Amazon Redshift event.

          

          

        Severity -> (string)

          

          The severity of the event.

           

          Values: ERROR, INFO

          

          

        

      

    

  



.. _Amazon Redshift Event Notifications: http://docs.aws.amazon.com/redshift/latest/mgmt/working-with-event-notifications.html
