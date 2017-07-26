[ :ref:`aws <cli:aws>` . :ref:`sns <cli:aws sns>` ]

.. _cli:aws sns list-subscriptions:


******************
list-subscriptions
******************



===========
Description
===========



Returns a list of the requester's subscriptions. Each call returns a limited list of subscriptions, up to 100. If there are more subscriptions, a ``NextToken`` is also returned. Use the ``NextToken`` parameter in a new ``list-subscriptions`` call to get further results.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sns-2010-03-31/ListSubscriptions>`_


``list-subscriptions`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Subscriptions``


========
Synopsis
========

::

    list-subscriptions
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

The following command retrieves a list of SNS subscriptions::

  aws sns list-subscriptions

Output::

  {
      "Subscriptions": [
          {
              "Owner": "0123456789012",
              "Endpoint": "my-email@example.com",
              "Protocol": "email",
              "TopicArn": "arn:aws:sns:us-west-2:0123456789012:my-topic",
              "SubscriptionArn": "arn:aws:sns:us-west-2:0123456789012:my-topic:8a21d249-4329-4871-acc6-7be709c6ea7f"
          }
      ]
  }


======
Output
======

Subscriptions -> (list)

  

  A list of subscriptions.

  

  (structure)

    

    A wrapper type for the attributes of an Amazon SNS subscription.

    

    SubscriptionArn -> (string)

      

      The subscription's ARN.

      

      

    Owner -> (string)

      

      The subscription's owner.

      

      

    Protocol -> (string)

      

      The subscription's protocol.

      

      

    Endpoint -> (string)

      

      The subscription's endpoint (format depends on the protocol).

      

      

    TopicArn -> (string)

      

      The ARN of the subscription's topic.

      

      

    

  

NextToken -> (string)

  

  Token to pass along to the next ``list-subscriptions`` request. This element is returned if there are more subscriptions to retrieve.

  

  

