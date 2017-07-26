[ :ref:`aws <cli:aws>` . :ref:`dms <cli:aws dms>` ]

.. _cli:aws dms delete-event-subscription:


*************************
delete-event-subscription
*************************



===========
Description
===========



Deletes an AWS DMS event subscription. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dms-2016-01-01/DeleteEventSubscription>`_


========
Synopsis
========

::

    delete-event-subscription
  --subscription-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--subscription-name`` (string)


  The name of the DMS event notification subscription to be deleted.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

EventSubscription -> (structure)

  

  The event subscription that was deleted.

  

  CustomerAwsId -> (string)

    

    The AWS customer account associated with the AWS DMS event notification subscription.

    

    

  CustSubscriptionId -> (string)

    

    The AWS DMS event notification subscription Id.

    

    

  SnsTopicArn -> (string)

    

    The topic ARN of the AWS DMS event notification subscription.

    

    

  Status -> (string)

    

    The status of the AWS DMS event notification subscription.

     

    Constraints:

     

    Can be one of the following: creating | modifying | deleting | active | no-permission | topic-not-exist

     

    The status "no-permission" indicates that AWS DMS no longer has permission to post to the SNS topic. The status "topic-not-exist" indicates that the topic was deleted after the subscription was created.

    

    

  SubscriptionCreationTime -> (string)

    

    The time the RDS event notification subscription was created.

    

    

  SourceType -> (string)

    

    The type of AWS DMS resource that generates events. 

     

    Valid values: replication-instance | replication-server | security-group | migration-task

    

    

  SourceIdsList -> (list)

    

    A list of source Ids for the event subscription.

    

    (string)

      

      

    

  EventCategoriesList -> (list)

    

    A lists of event categories.

    

    (string)

      

      

    

  Enabled -> (boolean)

    

    Boolean value that indicates if the event subscription is enabled.

    

    

  

