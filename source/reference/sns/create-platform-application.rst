[ :ref:`aws <cli:aws>` . :ref:`sns <cli:aws sns>` ]

.. _cli:aws sns create-platform-application:


***************************
create-platform-application
***************************



===========
Description
===========



Creates a platform application object for one of the supported push notification services, such as APNS and GCM, to which devices and mobile apps may register. You must specify PlatformPrincipal and PlatformCredential attributes when using the ``create-platform-application`` action. The PlatformPrincipal is received from the notification service. For APNS/APNS_SANDBOX, PlatformPrincipal is "SSL certificate". For GCM, PlatformPrincipal is not applicable. For ADM, PlatformPrincipal is "client id". The PlatformCredential is also received from the notification service. For APNS/APNS_SANDBOX, PlatformCredential is "private key". For GCM, PlatformCredential is "API key". For ADM, PlatformCredential is "client secret". The PlatformApplicationArn that is returned when using ``create-platform-application`` is then used as an attribute for the ``create-platform-endpoint`` action. For more information, see `Using Amazon SNS Mobile Push Notifications`_ . 



========
Synopsis
========

::

    create-platform-application
  --name <value>
  --platform <value>
  --attributes <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--name`` (string)


  Application names must be made up of only uppercase and lowercase ASCII letters, numbers, underscores, hyphens, and periods, and must be between 1 and 256 characters long.

  

``--platform`` (string)


  The following platforms are supported: ADM (Amazon Device Messaging), APNS (Apple Push Notification Service), APNS_SANDBOX, and GCM (Google Cloud Messaging).

  

``--attributes`` (map)


  For a list of attributes, see `set-platform-application-attributes`_ 

  



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

PlatformApplicationArn -> (string)

  

  PlatformApplicationArn is returned.

  

  



.. _Using Amazon SNS Mobile Push Notifications: http://docs.aws.amazon.com/sns/latest/dg/SNSMobilePush.html
.. _set-platform-application-attributes: http://docs.aws.amazon.com/sns/latest/api/API_SetPlatformApplicationAttributes.html
