[ :ref:`aws <cli:aws>` . :ref:`configservice <cli:aws configservice>` ]

.. _cli:aws configservice describe-delivery-channels:


**************************
describe-delivery-channels
**************************



===========
Description
===========



Returns details about the specified delivery channel. If a delivery channel is not specified, this action returns the details of all delivery channels associated with the account.

 

.. note::

   

  Currently, you can specify only one delivery channel per region in your account.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/config-2014-11-12/DescribeDeliveryChannels>`_


========
Synopsis
========

::

    describe-delivery-channels
  [--delivery-channel-names <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--delivery-channel-names`` (list)


  A list of delivery channel names.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get details about the delivery channel**

The following command returns details about the delivery channel::

    aws configservice describe-delivery-channels

Output::

    {
        "DeliveryChannels": [
            {
                "snsTopicARN": "arn:aws:sns:us-east-1:123456789012:config-topic",
                "name": "default",
                "s3BucketName": "config-bucket-123456789012"
            }
        ]
    }

======
Output
======

DeliveryChannels -> (list)

  

  A list that contains the descriptions of the specified delivery channel.

  

  (structure)

    

    The channel through which AWS Config delivers notifications and updated configuration states.

    

    name -> (string)

      

      The name of the delivery channel. By default, AWS Config assigns the name "default" when creating the delivery channel. To change the delivery channel name, you must use the delete-delivery-channel action to delete your current delivery channel, and then you must use the put-delivery-channel command to create a delivery channel that has the desired name.

      

      

    s3BucketName -> (string)

      

      The name of the Amazon S3 bucket to which AWS Config delivers configuration snapshots and configuration history files.

       

      If you specify a bucket that belongs to another AWS account, that bucket must have policies that grant access permissions to AWS Config. For more information, see `Permissions for the Amazon S3 Bucket <http://docs.aws.amazon.com/config/latest/developerguide/s3-bucket-policy.html>`_ in the AWS Config Developer Guide.

      

      

    s3KeyPrefix -> (string)

      

      The prefix for the specified Amazon S3 bucket.

      

      

    snsTopicARN -> (string)

      

      The Amazon Resource Name (ARN) of the Amazon SNS topic to which AWS Config sends notifications about configuration changes.

       

      If you choose a topic from another account, the topic must have policies that grant access permissions to AWS Config. For more information, see `Permissions for the Amazon SNS Topic <http://docs.aws.amazon.com/config/latest/developerguide/sns-topic-policy.html>`_ in the AWS Config Developer Guide.

      

      

    configSnapshotDeliveryProperties -> (structure)

      

      The options for how often AWS Config delivers configuration snapshots to the Amazon S3 bucket.

      

      deliveryFrequency -> (string)

        

        The frequency with which AWS Config delivers configuration snapshots.

        

        

      

    

  

