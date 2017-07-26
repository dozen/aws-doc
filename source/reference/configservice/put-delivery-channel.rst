[ :ref:`aws <cli:aws>` . :ref:`configservice <cli:aws configservice>` ]

.. _cli:aws configservice put-delivery-channel:


********************
put-delivery-channel
********************



===========
Description
===========



Creates a new delivery channel object to deliver the configuration information to an Amazon S3 bucket, and to an Amazon SNS topic. 

 

You can use this action to change the Amazon S3 bucket or an Amazon SNS topic of the existing delivery channel. To change the Amazon S3 bucket or an Amazon SNS topic, call this action and specify the changed values for the S3 bucket and the SNS topic. If you specify a different value for either the S3 bucket or the SNS topic, this action will keep the existing value for the parameter that is not changed. 

 

.. note::

   

  Currently, you can specify only one delivery channel per account.

   



========
Synopsis
========

::

    put-delivery-channel
  --delivery-channel <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To create a delivery channel**

The following command provides the settings for the delivery channel as JSON code::

    aws configservice put-delivery-channel --delivery-channel file://deliveryChannel.json

`deliveryChannel.json` is a JSON file that specifies the Amazon S3 bucket and Amazon SNS topic to which AWS Config will deliver configuration information::

    {
        "name": "default",
        "s3BucketName": "config-bucket-123456789012",
        "snsTopicARN": "arn:aws:sns:us-east-1:123456789012:config-topic"
    }

If the command succeeds, AWS Config returns no output. To verify the settings of your delivery channel, run the `describe-delivery-channels`__ command.

.. __: http://docs.aws.amazon.com/cli/latest/reference/configservice/describe-delivery-channels.html

======
Output
======

None