[ :ref:`aws <cli:aws>` . :ref:`sns <cli:aws sns>` ]

.. _cli:aws sns list-subscriptions-by-topic:


***************************
list-subscriptions-by-topic
***************************



===========
Description
===========



Returns a list of the subscriptions to a specific topic. Each call returns a limited list of subscriptions, up to 100. If there are more subscriptions, a ``NextToken`` is also returned. Use the ``NextToken`` parameter in a new ``list-subscriptions-by-topic`` call to get further results.



``list-subscriptions-by-topic`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Subscriptions``


========
Synopsis
========

::

    list-subscriptions-by-topic
  --topic-arn <value>
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--topic-arn`` (string)


  The ARN of the topic for which you wish to find subscriptions.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command retrieves a list of SNS subscriptions::

  aws sns list-subscriptions-by-topic --topic-arn "arn:aws:sns:us-west-2:0123456789012:my-topic"

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

  

  Token to pass along to the next ``list-subscriptions-by-topic`` request. This element is returned if there are more subscriptions to retrieve.

  

  

