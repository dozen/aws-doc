[ :ref:`aws <cli:aws>` . :ref:`configservice <cli:aws configservice>` ]

.. _cli:aws configservice describe-delivery-channel-status:


********************************
describe-delivery-channel-status
********************************



===========
Description
===========



Returns the current status of the specified delivery channel. If a delivery channel is not specified, this action returns the current status of all delivery channels associated with the account. 

 

.. note::

  Currently, you can specify only one delivery channel per account.



========
Synopsis
========

::

    describe-delivery-channel-status
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

**To get status information for the delivery channel**

The following command returns the status of the delivery channel::

    aws configservice describe-delivery-channel-status

Output::

    {
        "DeliveryChannelsStatus": [
            {
                "configStreamDeliveryInfo": {
                    "lastStatusChangeTime": 1452193834.381,
                    "lastStatus": "SUCCESS"
                },
                "configHistoryDeliveryInfo": {
                    "lastSuccessfulTime": 1450317838.412,
                    "lastStatus": "SUCCESS",
                    "lastAttemptTime": 1450317838.412
                },
                "configSnapshotDeliveryInfo": {
                    "lastSuccessfulTime": 1452185597.094,
                    "lastStatus": "SUCCESS",
                    "lastAttemptTime": 1452185597.094
                },
                "name": "default"
            }
        ]
    }

======
Output
======

DeliveryChannelsStatus -> (list)

  

  A list that contains the status of a specified delivery channel.

  

  (structure)

    

    The status of a specified delivery channel.

     

    Valid values: ``Success`` | ``Failure`` 

    

    name -> (string)

      

      The name of the delivery channel.

      

      

    configSnapshotDeliveryInfo -> (structure)

      

      A list containing the status of the delivery of the snapshot to the specified Amazon S3 bucket.

      

      lastStatus -> (string)

        

        Status of the last attempted delivery.

        

        

      lastErrorCode -> (string)

        

        The error code from the last attempted delivery.

        

        

      lastErrorMessage -> (string)

        

        The error message from the last attempted delivery.

        

        

      lastAttemptTime -> (timestamp)

        

        The time of the last attempted delivery.

        

        

      lastSuccessfulTime -> (timestamp)

        

        The time of the last successful delivery.

        

        

      nextDeliveryTime -> (timestamp)

        

        The time that the next delivery occurs.

        

        

      

    configHistoryDeliveryInfo -> (structure)

      

      A list that contains the status of the delivery of the configuration history to the specified Amazon S3 bucket.

      

      lastStatus -> (string)

        

        Status of the last attempted delivery.

        

        

      lastErrorCode -> (string)

        

        The error code from the last attempted delivery.

        

        

      lastErrorMessage -> (string)

        

        The error message from the last attempted delivery.

        

        

      lastAttemptTime -> (timestamp)

        

        The time of the last attempted delivery.

        

        

      lastSuccessfulTime -> (timestamp)

        

        The time of the last successful delivery.

        

        

      nextDeliveryTime -> (timestamp)

        

        The time that the next delivery occurs.

        

        

      

    configStreamDeliveryInfo -> (structure)

      

      A list containing the status of the delivery of the configuration stream notification to the specified Amazon SNS topic.

      

      lastStatus -> (string)

        

        Status of the last attempted delivery.

         

        **Note** Providing an SNS topic on a `DeliveryChannel`_ for AWS Config is optional. If the SNS delivery is turned off, the last status will be **Not_Applicable** .

        

        

      lastErrorCode -> (string)

        

        The error code from the last attempted delivery.

        

        

      lastErrorMessage -> (string)

        

        The error message from the last attempted delivery.

        

        

      lastStatusChangeTime -> (timestamp)

        

        The time from the last status change.

        

        

      

    

  



.. _DeliveryChannel: http://docs.aws.amazon.com/config/latest/APIReference/API_DeliveryChannel.html
