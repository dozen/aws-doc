[ :ref:`aws <cli:aws>` . :ref:`sns <cli:aws sns>` ]

.. _cli:aws sns get-topic-attributes:


********************
get-topic-attributes
********************



===========
Description
===========



Returns all of the properties of a topic. Topic properties returned might differ based on the authorization of the user. 



========
Synopsis
========

::

    get-topic-attributes
  --topic-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--topic-arn`` (string)


  The ARN of the topic whose properties you want to get.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command gets the attributes of a topic named ``my-topic``::

  aws sns get-topic-attributes --topic-arn "arn:aws:sns:us-west-2:0123456789012:my-topic"

Output::

  {
      "Attributes": {
          "SubscriptionsConfirmed": "1",
          "DisplayName": "my-topic",
          "SubscriptionsDeleted": "0",
          "EffectiveDeliveryPolicy": "{\"http\":{\"defaultHealthyRetryPolicy\":{\"minDelayTarget\":20,\"maxDelayTarget\":20,\"numRetries\":3,\"numMaxDelayRetries\":0,\"numNoDelayRetries\":0,\"numMinDelayRetries\":0,\"backoffFunction\":\"linear\"},\"disableSubscriptionOverrides\":false}}",
          "Owner": "0123456789012",
          "Policy": "{\"Version\":\"2008-10-17\",\"Id\":\"__default_policy_ID\",\"Statement\":[{\"Sid\":\"__default_statement_ID\",\"Effect\":\"Allow\",\"Principal\":{\"AWS\":\"*\"},\"Action\":[\"SNS:Subscribe\",\"SNS:ListSubscriptionsByTopic\",\"SNS:DeleteTopic\",\"SNS:GetTopicAttributes\",\"SNS:Publish\",\"SNS:RemovePermission\",\"SNS:AddPermission\",\"SNS:Receive\",\"SNS:SetTopicAttributes\"],\"Resource\":\"arn:aws:sns:us-west-2:0123456789012:my-topic\",\"Condition\":{\"StringEquals\":{\"AWS:SourceOwner\":\"0123456789012\"}}}]}",
          "TopicArn": "arn:aws:sns:us-west-2:0123456789012:my-topic",
          "SubscriptionsPending": "0"
      }
  }


======
Output
======

Attributes -> (map)

  

  A map of the topic's attributes. Attributes in this map include the following:

   

   
  * ``TopicArn`` -- the topic's ARN
   
  * ``Owner`` -- the AWS account ID of the topic's owner
   
  * ``Policy`` -- the JSON serialization of the topic's access control policy
   
  * ``DisplayName`` -- the human-readable name used in the "From" field for notifications to email and email-json endpoints
   
  * ``SubscriptionsPending`` -- the number of subscriptions pending confirmation on this topic
   
  * ``SubscriptionsConfirmed`` -- the number of confirmed subscriptions on this topic
   
  * ``SubscriptionsDeleted`` -- the number of deleted subscriptions on this topic
   
  * ``DeliveryPolicy`` -- the JSON serialization of the topic's delivery policy
   
  * ``EffectiveDeliveryPolicy`` -- the JSON serialization of the effective delivery policy that takes into account system defaults
   

  

  key -> (string)

    

    

  value -> (string)

    

    

  

