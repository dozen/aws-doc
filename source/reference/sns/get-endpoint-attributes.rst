[ :ref:`aws <cli:aws>` . :ref:`sns <cli:aws sns>` ]

.. _cli:aws sns get-endpoint-attributes:


***********************
get-endpoint-attributes
***********************



===========
Description
===========



Retrieves the endpoint attributes for a device on one of the supported push notification services, such as GCM and APNS. For more information, see `Using Amazon SNS Mobile Push Notifications`_ . 



========
Synopsis
========

::

    get-endpoint-attributes
  --endpoint-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--endpoint-arn`` (string)


  EndpointArn for get-endpoint-attributes input.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Attributes -> (map)

  

  Attributes include the following:

   

   
  * ``CustomUserData`` -- arbitrary user data to associate with the endpoint. Amazon SNS does not use this data. The data must be in UTF-8 format and less than 2KB.
   
  * ``Enabled`` -- flag that enables/disables delivery to the endpoint. Amazon SNS will set this to false when a notification service indicates to Amazon SNS that the endpoint is invalid. Users can set it back to true, typically after updating Token.
   
  * ``Token`` -- device token, also referred to as a registration id, for an app and mobile device. This is returned from the notification service when an app and mobile device are registered with the notification service.
   

  

  key -> (string)

    

    

  value -> (string)

    

    

  



.. _Using Amazon SNS Mobile Push Notifications: http://docs.aws.amazon.com/sns/latest/dg/SNSMobilePush.html
