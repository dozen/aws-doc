[ :ref:`aws <cli:aws>` . :ref:`dms <cli:aws dms>` ]

.. _cli:aws dms modify-event-subscription:


*************************
modify-event-subscription
*************************



===========
Description
===========



Modifies an existing AWS DMS event notification subscription. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dms-2016-01-01/ModifyEventSubscription>`_


========
Synopsis
========

::

    modify-event-subscription
  --subscription-name <value>
  [--sns-topic-arn <value>]
  [--source-type <value>]
  [--event-categories <value>]
  [--enabled | --no-enabled]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--subscription-name`` (string)


  The name of the AWS DMS event notification subscription to be modified.

  

``--sns-topic-arn`` (string)


  The Amazon Resource Name (ARN) of the Amazon SNS topic created for event notification. The ARN is created by Amazon SNS when you create a topic and subscribe to it.

  

``--source-type`` (string)


  The type of AWS DMS resource that generates the events you want to subscribe to. 

   

  Valid values: replication-instance | migration-task

  

``--event-categories`` (list)


  A list of event categories for a source type that you want to subscribe to. Use the ``describe-event-categories`` action to see a list of event categories. 

  



Syntax::

  "string" "string" ...



``--enabled`` | ``--no-enabled`` (boolean)


  A Boolean value; set to **true** to activate the subscription. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

EventSubscription -> (structure)

  

  The modified event subscription.

  

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

    

    

  

