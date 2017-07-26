[ :ref:`aws <cli:aws>` . :ref:`configservice <cli:aws configservice>` ]

.. _cli:aws configservice put-delivery-channel:


********************
put-delivery-channel
********************



===========
Description
===========



Creates a delivery channel object to deliver configuration information to an Amazon S3 bucket and Amazon SNS topic.

 

Before you can create a delivery channel, you must create a configuration recorder.

 

You can use this action to change the Amazon S3 bucket or an Amazon SNS topic of the existing delivery channel. To change the Amazon S3 bucket or an Amazon SNS topic, call this action and specify the changed values for the S3 bucket and the SNS topic. If you specify a different value for either the S3 bucket or the SNS topic, this action will keep the existing value for the parameter that is not changed.

 

.. note::

   

  You can have only one delivery channel per region in your account.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/config-2014-11-12/PutDeliveryChannel>`_


========
Synopsis
========

::

    put-delivery-channel
  --delivery-channel <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--delivery-channel`` (structure)


  The configuration delivery channel object that delivers the configuration information to an Amazon S3 bucket, and to an Amazon SNS topic.

  



Shorthand Syntax::

    name=string,s3BucketName=string,s3KeyPrefix=string,snsTopicARN=string,configSnapshotDeliveryProperties={deliveryFrequency=string}




JSON Syntax::

  {
    "name": "string",
    "s3BucketName": "string",
    "s3KeyPrefix": "string",
    "snsTopicARN": "string",
    "configSnapshotDeliveryProperties": {
      "deliveryFrequency": "One_Hour"|"Three_Hours"|"Six_Hours"|"Twelve_Hours"|"TwentyFour_Hours"
    }
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a delivery channel**

The following command provides the settings for the delivery channel as JSON code::

    aws configservice put-delivery-channel --delivery-channel file://deliveryChannel.json

The ``deliveryChannel.json`` file specifies the delivery channel attributes::

    {
        "name": "default",
        "s3BucketName": "config-bucket-123456789012",
        "snsTopicARN": "arn:aws:sns:us-east-1:123456789012:config-topic",
        "configSnapshotDeliveryProperties": {
            "deliveryFrequency": "Twelve_Hours"
        }
    }

This example sets the following attributes:

- ``name`` - The name of the delivery channel. By default, AWS Config assigns the name ``default`` to a new delivery channel.

  You cannot update the delivery channel name with the ``put-delivery-channel`` command. For the steps to change the name, see `Renaming the Delivery Channel`__. 

  .. __: http://docs.aws.amazon.com/config/latest/developerguide/update-dc.html#update-dc-rename

- ``s3BucketName`` - The name of the Amazon S3 bucket to which AWS Config delivers configuration snapshots and configuration history files.

  If you specify a bucket that belongs to another AWS account, that bucket must have policies that grant access permissions to AWS Config. For more information, see `Permissions for the Amazon S3 Bucket`__.

.. __: http://docs.aws.amazon.com/config/latest/developerguide/s3-bucket-policy.html

- ``snsTopicARN`` - The Amazon Resource Name (ARN) of the Amazon SNS topic to which AWS Config sends notifications about configuration changes.

  If you choose a topic from another account, the topic must have policies that grant access permissions to AWS Config. For more information, see `Permissions for the Amazon SNS Topic`__.

.. __: http://docs.aws.amazon.com/config/latest/developerguide/sns-topic-policy.html

- ``configSnapshotDeliveryProperties`` - Contains the ``deliveryFrequency`` attribute, which sets how often AWS Config delivers configuration snapshots and how often it invokes evaluations for periodic Config rules.

If the command succeeds, AWS Config returns no output. To verify the settings of your delivery channel, run the `describe-delivery-channels`__ command.

.. __: http://docs.aws.amazon.com/cli/latest/reference/configservice/describe-delivery-channels.html

======
Output
======

None