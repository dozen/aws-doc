[ :ref:`aws <cli:aws>` . :ref:`sns <cli:aws sns>` ]

.. _cli:aws sns create-platform-endpoint:


************************
create-platform-endpoint
************************



===========
Description
===========



Creates an endpoint for a device and mobile app on one of the supported push notification services, such as GCM and APNS. ``create-platform-endpoint`` requires the PlatformApplicationArn that is returned from ``create-platform-application`` . The EndpointArn that is returned when using ``create-platform-endpoint`` can then be used by the ``publish`` action to send a message to a mobile app or by the ``subscribe`` action for subscription to a topic. The ``create-platform-endpoint`` action is idempotent, so if the requester already owns an endpoint with the same device token and attributes, that endpoint's ARN is returned without creating a new endpoint. For more information, see `Using Amazon SNS Mobile Push Notifications`_ . 

 

When using ``create-platform-endpoint`` with Baidu, two attributes must be provided: ChannelId and UserId. The token field must also contain the ChannelId. For more information, see `Creating an Amazon SNS Endpoint for Baidu`_ . 



========
Synopsis
========

::

    create-platform-endpoint
  --platform-application-arn <value>
  --token <value>
  [--custom-user-data <value>]
  [--attributes <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--platform-application-arn`` (string)


  PlatformApplicationArn returned from create-platform-application is used to create a an endpoint.

  

``--token`` (string)


  Unique identifier created by the notification service for an app on a device. The specific name for Token will vary, depending on which notification service is being used. For example, when using APNS as the notification service, you need the device token. Alternatively, when using GCM or ADM, the device token equivalent is called the registration ID.

  

``--custom-user-data`` (string)


  Arbitrary user data to associate with the endpoint. Amazon SNS does not use this data. The data must be in UTF-8 format and less than 2KB.

  

``--attributes`` (map)


  For a list of attributes, see `set-endpoint-attributes`_ .

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

EndpointArn -> (string)

  

  EndpointArn returned from CreateEndpoint action.

  

  



.. _Using Amazon SNS Mobile Push Notifications: http://docs.aws.amazon.com/sns/latest/dg/SNSMobilePush.html
.. _set-endpoint-attributes: http://docs.aws.amazon.com/sns/latest/api/API_SetEndpointAttributes.html
.. _Creating an Amazon SNS Endpoint for Baidu: http://docs.aws.amazon.com/sns/latest/dg/SNSMobilePushBaiduEndpoint.html
