[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds remove-source-identifier-from-subscription:


******************************************
remove-source-identifier-from-subscription
******************************************



===========
Description
===========



Removes a source identifier from an existing RDS event notification subscription.



========
Synopsis
========

::

    remove-source-identifier-from-subscription
  --subscription-name <value>
  --source-identifier <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--subscription-name`` (string)


  The name of the RDS event notification subscription you want to remove a source identifier from.

  

``--source-identifier`` (string)


  The source identifier to be removed from the subscription, such as the **DB instance identifier** for a DB instance or the name of a security group. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

EventSubscription -> (structure)

  

  Contains the results of a successful invocation of the  describe-event-subscriptions action.

  

  CustomerAwsId -> (string)

    

    The AWS customer account associated with the RDS event notification subscription.

    

    

  CustSubscriptionId -> (string)

    

    The RDS event notification subscription Id.

    

    

  SnsTopicArn -> (string)

    

    The topic ARN of the RDS event notification subscription.

    

    

  Status -> (string)

    

    The status of the RDS event notification subscription.

     

    Constraints:

     

    Can be one of the following: creating | modifying | deleting | active | no-permission | topic-not-exist

     

    The status "no-permission" indicates that RDS no longer has permission to post to the SNS topic. The status "topic-not-exist" indicates that the topic was deleted after the subscription was created.

    

    

  SubscriptionCreationTime -> (string)

    

    The time the RDS event notification subscription was created.

    

    

  SourceType -> (string)

    

    The source type for the RDS event notification subscription.

    

    

  SourceIdsList -> (list)

    

    A list of source IDs for the RDS event notification subscription.

    

    (string)

      

      

    

  EventCategoriesList -> (list)

    

    A list of event categories for the RDS event notification subscription.

    

    (string)

      

      

    

  Enabled -> (boolean)

    

    A Boolean value indicating if the subscription is enabled. True indicates the subscription is enabled.

    

    

  

