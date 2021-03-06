[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift modify-event-subscription:


*************************
modify-event-subscription
*************************



===========
Description
===========



Modifies an existing Amazon Redshift event notification subscription.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/redshift-2012-12-01/ModifyEventSubscription>`_


========
Synopsis
========

::

    modify-event-subscription
  --subscription-name <value>
  [--sns-topic-arn <value>]
  [--source-type <value>]
  [--source-ids <value>]
  [--event-categories <value>]
  [--severity <value>]
  [--enabled | --no-enabled]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--subscription-name`` (string)


  The name of the modified Amazon Redshift event notification subscription.

  

``--sns-topic-arn`` (string)


  The Amazon Resource Name (ARN) of the SNS topic to be used by the event notification subscription.

  

``--source-type`` (string)


  The type of source that will be generating the events. For example, if you want to be notified of events generated by a cluster, you would set this parameter to cluster. If this value is not specified, events are returned for all Amazon Redshift objects in your AWS account. You must specify a source type in order to specify source IDs.

   

  Valid values: cluster, cluster-parameter-group, cluster-security-group, and cluster-snapshot.

  

``--source-ids`` (list)


  A list of one or more identifiers of Amazon Redshift source objects. All of the objects must be of the same type as was specified in the source type parameter. The event subscription will return only events generated by the specified objects. If not specified, then events are returned for all objects within the source type specified.

   

  Example: my-cluster-1, my-cluster-2

   

  Example: my-snapshot-20131010

  



Syntax::

  "string" "string" ...



``--event-categories`` (list)


  Specifies the Amazon Redshift event categories to be published by the event notification subscription.

   

  Values: Configuration, Management, Monitoring, Security

  



Syntax::

  "string" "string" ...



``--severity`` (string)


  Specifies the Amazon Redshift event severity to be published by the event notification subscription.

   

  Values: ERROR, INFO

  

``--enabled`` | ``--no-enabled`` (boolean)


  A Boolean value indicating if the subscription is enabled. ``true`` indicates the subscription is enabled 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

EventSubscription -> (structure)

  

  Describes event subscriptions.

  

  CustomerAwsId -> (string)

    

    The AWS customer account associated with the Amazon Redshift event notification subscription.

    

    

  CustSubscriptionId -> (string)

    

    The name of the Amazon Redshift event notification subscription.

    

    

  SnsTopicArn -> (string)

    

    The Amazon Resource Name (ARN) of the Amazon SNS topic used by the event notification subscription.

    

    

  Status -> (string)

    

    The status of the Amazon Redshift event notification subscription.

     

    Constraints:

     

     
    * Can be one of the following: active | no-permission | topic-not-exist 
     
    * The status "no-permission" indicates that Amazon Redshift no longer has permission to post to the Amazon SNS topic. The status "topic-not-exist" indicates that the topic was deleted after the subscription was created. 
     

    

    

  SubscriptionCreationTime -> (timestamp)

    

    The date and time the Amazon Redshift event notification subscription was created.

    

    

  SourceType -> (string)

    

    The source type of the events returned the Amazon Redshift event notification, such as cluster, or cluster-snapshot.

    

    

  SourceIdsList -> (list)

    

    A list of the sources that publish events to the Amazon Redshift event notification subscription.

    

    (string)

      

      

    

  EventCategoriesList -> (list)

    

    The list of Amazon Redshift event categories specified in the event notification subscription.

     

    Values: Configuration, Management, Monitoring, Security

    

    (string)

      

      

    

  Severity -> (string)

    

    The event severity specified in the Amazon Redshift event notification subscription.

     

    Values: ERROR, INFO

    

    

  Enabled -> (boolean)

    

    A Boolean value indicating whether the subscription is enabled. ``true`` indicates the subscription is enabled.

    

    

  Tags -> (list)

    

    The list of tags for the event subscription.

    

    (structure)

      

      A tag consisting of a name/value pair for a resource.

      

      Key -> (string)

        

        The key, or name, for the resource tag.

        

        

      Value -> (string)

        

        The value for the resource tag.

        

        

      

    

  

