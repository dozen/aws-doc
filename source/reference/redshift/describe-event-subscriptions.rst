[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift describe-event-subscriptions:


****************************
describe-event-subscriptions
****************************



===========
Description
===========



Lists descriptions of all the Amazon Redshift event notifications subscription for a customer account. If you specify a subscription name, lists the description for that subscription. 



``describe-event-subscriptions`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``EventSubscriptionsList``


========
Synopsis
========

::

    describe-event-subscriptions
  [--subscription-name <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--subscription-name`` (string)


  The name of the Amazon Redshift event notification subscription to be described.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Marker -> (string)

  

  A value that indicates the starting point for the next set of response records in a subsequent request. If a value is returned in a response, you can retrieve the next set of records by providing this returned marker value in the ``Marker`` parameter and retrying the command. If the ``Marker`` field is empty, all response records have been retrieved for the request. 

  

  

EventSubscriptionsList -> (list)

  

  A list of event subscriptions.

  

  (structure)

    

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

          

          

        

      

    

  

