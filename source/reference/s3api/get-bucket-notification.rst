[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api get-bucket-notification:


***********************
get-bucket-notification
***********************



===========
Description
===========

Deprecated, see the get-bucket-notification-configuration operation.

========
Synopsis
========

::

    get-bucket-notification
  --bucket <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--bucket`` (string)
Name of the buket to get the notification configuration for.

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command retrieves the notification configuration for a bucket named ``my-bucket``::

  aws s3api get-bucket-notification --bucket my-bucket

Output::

  {
      "TopicConfiguration": {
          "Topic": "arn:aws:sns:us-west-2:123456789012:my-notification-topic",
          "Id": "YmQzMmEwM2EjZWVlI0NGItNzVtZjI1MC00ZjgyLWZDBiZWNl",
          "Event": "s3:ObjectCreated:*",
          "Events": [
              "s3:ObjectCreated:*"
          ]
      }
  }


======
Output
======

TopicConfiguration -> (structure)

  

  Id -> (string)

    Optional unique identifier for configurations in a notification configuration. If you don't provide one, Amazon S3 will assign an ID.

    

  Events -> (list)

    

    (string)

      Bucket event for which to send notifications.

      

    

  Event -> (string)

    Bucket event for which to send notifications.

    

  Topic -> (string)

    Amazon SNS topic to which Amazon S3 will publish a message to report the specified events for the bucket.

    

  

QueueConfiguration -> (structure)

  

  Id -> (string)

    Optional unique identifier for configurations in a notification configuration. If you don't provide one, Amazon S3 will assign an ID.

    

  Event -> (string)

    Bucket event for which to send notifications.

    

  Events -> (list)

    

    (string)

      Bucket event for which to send notifications.

      

    

  Queue -> (string)

    

    

  

CloudFunctionConfiguration -> (structure)

  

  Id -> (string)

    Optional unique identifier for configurations in a notification configuration. If you don't provide one, Amazon S3 will assign an ID.

    

  Event -> (string)

    Bucket event for which to send notifications.

    

  Events -> (list)

    

    (string)

      Bucket event for which to send notifications.

      

    

  CloudFunction -> (string)

    

    

  InvocationRole -> (string)

    

    

  

