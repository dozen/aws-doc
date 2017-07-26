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

   

  Currently, you can specify only one delivery channel per account.

   



========
Synopsis
========

::

    describe-delivery-channels
  [--delivery-channel-names <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--delivery-channel-names`` (list)


  A list of delivery channel names.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

    

    A logical container used for storing the configuration changes of an AWS resource.

    

    name -> (string)

      

      The name of the delivery channel. By default, AWS Config automatically assigns the name defaultwhen creating the delivery channel. You cannot change the assigned name. 

      

      

    s3BucketName -> (string)

      

      The name of the Amazon S3 bucket used to store configuration history for the delivery channel.

      

      

    s3KeyPrefix -> (string)

      

      The prefix for the specified Amazon S3 bucket.

      

      

    snsTopicARN -> (string)

      

      The Amazon Resource Name (ARN) of the SNS topic that AWS Config delivers notifications to.

      

      

    configSnapshotDeliveryProperties -> (structure)

      

      Options for how AWS Config delivers configuration snapshots to the Amazon S3 bucket in your delivery channel.

      

      deliveryFrequency -> (string)

        

        The frequency with which a AWS Config recurringly delivers configuration snapshots.

        

        

      

    

  

