[ :ref:`aws <cli:aws>` . :ref:`dms <cli:aws dms>` ]

.. _cli:aws dms describe-event-subscriptions:


****************************
describe-event-subscriptions
****************************



===========
Description
===========



Lists all the event subscriptions for a customer account. The description of a subscription includes ``SubscriptionName`` , ``SNSTopicARN`` , ``CustomerID`` , ``SourceType`` , ``SourceID`` , ``CreationTime`` , and ``Status`` . 

 

If you specify ``SubscriptionName`` , this action lists the description for that subscription.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dms-2016-01-01/DescribeEventSubscriptions>`_


========
Synopsis
========

::

    describe-event-subscriptions
  [--subscription-name <value>]
  [--filters <value>]
  [--max-records <value>]
  [--marker <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--subscription-name`` (string)


  The name of the AWS DMS event subscription to be described.

  

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



``--max-records`` (integer)


  The maximum number of records to include in the response. If more records exist than the specified ``MaxRecords`` value, a pagination token called a marker is included in the response so that the remaining results can be retrieved. 

   

  Default: 100

   

  Constraints: Minimum 20, maximum 100.

  

``--marker`` (string)


  An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Marker -> (string)

  

  An optional pagination token provided by a previous request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

  

  

EventSubscriptionsList -> (list)

  

  A list of event subscriptions.

  

  (structure)

    

    

    

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

      

      

    

  

