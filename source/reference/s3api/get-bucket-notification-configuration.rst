[ :ref:`aws <cli:aws>` . :ref:`s3api <cli:aws s3api>` ]

.. _cli:aws s3api get-bucket-notification-configuration:


*************************************
get-bucket-notification-configuration
*************************************



===========
Description
===========

Returns the notification configuration of a bucket.

========
Synopsis
========

::

    get-bucket-notification-configuration
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

  aws s3api get-bucket-notification-configuration --bucket my-bucket

Output::

  {
      "TopicConfigurations": [
          {
              "Id": "YmQzMmEwM2EjZWVlI0NGItNzVtZjI1MC00ZjgyLWZDBiZWNl",
              "TopicArn": "arn:aws:sns:us-west-2:123456789012:my-notification-topic",
              "Events": [
                  "s3:ObjectCreated:*"
              ]
          }
      ]
  }


======
Output
======

TopicConfigurations -> (list)

  

  (structure)

    Container for specifying the configuration when you want Amazon S3 to publish events to an Amazon Simple Notification Service (Amazon SNS) topic.

    Id -> (string)

      Optional unique identifier for configurations in a notification configuration. If you don't provide one, Amazon S3 will assign an ID.

      

    TopicArn -> (string)

      Amazon SNS topic ARN to which Amazon S3 will publish a message when it detects events of specified type.

      

    Events -> (list)

      

      (string)

        Bucket event for which to send notifications.

        

      

    Filter -> (structure)

      Container for object key name filtering rules. For information about key name filtering, go to `Configuring Event Notifications`_ in the Amazon Simple Storage Service Developer Guide.

      Key -> (structure)

        Container for object key name prefix and suffix filtering rules.

        FilterRules -> (list)

          A list of containers for key value pair that defines the criteria for the filter rule.

          (structure)

            Container for key value pair that defines the criteria for the filter rule.

            Name -> (string)

              Object key name prefix or suffix identifying one or more objects to which the filtering rule applies. Maximum prefix length can be up to 1,024 characters. Overlapping prefixes and suffixes are not supported. For more information, go to `Configuring Event Notifications`_ in the Amazon Simple Storage Service Developer Guide.

              

            Value -> (string)

              

              

            

          

        

      

    

  

QueueConfigurations -> (list)

  

  (structure)

    Container for specifying an configuration when you want Amazon S3 to publish events to an Amazon Simple Queue Service (Amazon SQS) queue.

    Id -> (string)

      Optional unique identifier for configurations in a notification configuration. If you don't provide one, Amazon S3 will assign an ID.

      

    QueueArn -> (string)

      Amazon SQS queue ARN to which Amazon S3 will publish a message when it detects events of specified type.

      

    Events -> (list)

      

      (string)

        Bucket event for which to send notifications.

        

      

    Filter -> (structure)

      Container for object key name filtering rules. For information about key name filtering, go to `Configuring Event Notifications`_ in the Amazon Simple Storage Service Developer Guide.

      Key -> (structure)

        Container for object key name prefix and suffix filtering rules.

        FilterRules -> (list)

          A list of containers for key value pair that defines the criteria for the filter rule.

          (structure)

            Container for key value pair that defines the criteria for the filter rule.

            Name -> (string)

              Object key name prefix or suffix identifying one or more objects to which the filtering rule applies. Maximum prefix length can be up to 1,024 characters. Overlapping prefixes and suffixes are not supported. For more information, go to `Configuring Event Notifications`_ in the Amazon Simple Storage Service Developer Guide.

              

            Value -> (string)

              

              

            

          

        

      

    

  

LambdaFunctionConfigurations -> (list)

  

  (structure)

    Container for specifying the AWS Lambda notification configuration.

    Id -> (string)

      Optional unique identifier for configurations in a notification configuration. If you don't provide one, Amazon S3 will assign an ID.

      

    LambdaFunctionArn -> (string)

      Lambda cloud function ARN that Amazon S3 can invoke when it detects events of the specified type.

      

    Events -> (list)

      

      (string)

        Bucket event for which to send notifications.

        

      

    Filter -> (structure)

      Container for object key name filtering rules. For information about key name filtering, go to `Configuring Event Notifications`_ in the Amazon Simple Storage Service Developer Guide.

      Key -> (structure)

        Container for object key name prefix and suffix filtering rules.

        FilterRules -> (list)

          A list of containers for key value pair that defines the criteria for the filter rule.

          (structure)

            Container for key value pair that defines the criteria for the filter rule.

            Name -> (string)

              Object key name prefix or suffix identifying one or more objects to which the filtering rule applies. Maximum prefix length can be up to 1,024 characters. Overlapping prefixes and suffixes are not supported. For more information, go to `Configuring Event Notifications`_ in the Amazon Simple Storage Service Developer Guide.

              

            Value -> (string)

              

              

            

          

        

      

    

  



.. _Configuring Event Notifications: http://docs.aws.amazon.com/AmazonS3/latest/dev/NotificationHowTo.html
