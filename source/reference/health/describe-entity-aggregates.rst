[ :ref:`aws <cli:aws>` . :ref:`health <cli:aws health>` ]

.. _cli:aws health describe-entity-aggregates:


**************************
describe-entity-aggregates
**************************



===========
Description
===========



Returns the number of entities that are affected by each of the specified events. If no events are specified, the counts of all affected entities are returned.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/health-2016-08-04/DescribeEntityAggregates>`_


========
Synopsis
========

::

    describe-entity-aggregates
  [--event-arns <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--event-arns`` (list)


  A list of event ARNs (unique identifiers). For example: ``"arn:aws:health:us-east-1::event/AWS_EC2_MAINTENANCE_5331", "arn:aws:health:us-west-1::event/AWS_EBS_LOST_VOLUME_xyz"``  

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

entityAggregates -> (list)

  

  The number of entities that are affected by each of the specified events.

  

  (structure)

    

    The number of entities that are affected by one or more events. Returned by the  describe-entity-aggregates operation.

    

    eventArn -> (string)

      

      The unique identifier for the event. Format: ``arn:aws:health:*event-region* ::event/*EVENT_TYPE_PLUS_ID* `` . Example: ``arn:aws:health:us-east-1::event/AWS_EC2_MAINTENANCE_5331``  

      

      

    count -> (integer)

      

      The number entities that match the criteria for the specified events.

      

      

    

  

