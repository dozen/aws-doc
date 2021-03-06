[ :ref:`aws <cli:aws>` . :ref:`rds <cli:aws rds>` ]

.. _cli:aws rds describe-event-subscriptions:


****************************
describe-event-subscriptions
****************************



===========
Description
===========



Lists all the subscription descriptions for a customer account. The description for a subscription includes SubscriptionName, SNSTopicARN, CustomerID, SourceType, SourceID, CreationTime, and Status.

 

If you specify a SubscriptionName, lists the description for that subscription.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/rds-2014-10-31/DescribeEventSubscriptions>`_


``describe-event-subscriptions`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``EventSubscriptionsList``


========
Synopsis
========

::

    describe-event-subscriptions
  [--subscription-name <value>]
  [--filters <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--subscription-name`` (string)


  The name of the RDS event notification subscription you want to describe.

  

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

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Marker -> (string)

  

  An optional pagination token provided by a previous describe-orderable-db-instance-options request. If this parameter is specified, the response includes only records beyond the marker, up to the value specified by ``MaxRecords`` . 

  

  

EventSubscriptionsList -> (list)

  

  A list of EventSubscriptions data types.

  

  (structure)

    

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

      

      

    EventSubscriptionArn -> (string)

      

      The Amazon Resource Name (ARN) for the event subscription.

      

      

    

  

