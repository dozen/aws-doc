[ :ref:`aws <cli:aws>` . :ref:`sns <cli:aws sns>` ]

.. _cli:aws sns create-platform-application:


***************************
create-platform-application
***************************



===========
Description
===========



Creates a platform application object for one of the supported push notification services, such as APNS and GCM, to which devices and mobile apps may register. You must specify PlatformPrincipal and PlatformCredential attributes when using the ``create-platform-application`` action. The PlatformPrincipal is received from the notification service. For APNS/APNS_SANDBOX, PlatformPrincipal is "SSL certificate". For GCM, PlatformPrincipal is not applicable. For ADM, PlatformPrincipal is "client id". The PlatformCredential is also received from the notification service. For WNS, PlatformPrincipal is "Package Security Identifier". For MPNS, PlatformPrincipal is "TLS certificate". For Baidu, PlatformPrincipal is "API key".

 

For APNS/APNS_SANDBOX, PlatformCredential is "private key". For GCM, PlatformCredential is "API key". For ADM, PlatformCredential is "client secret". For WNS, PlatformCredential is "secret key". For MPNS, PlatformCredential is "private key". For Baidu, PlatformCredential is "secret key". The PlatformApplicationArn that is returned when using ``create-platform-application`` is then used as an attribute for the ``create-platform-endpoint`` action. For more information, see `Using Amazon SNS Mobile Push Notifications <http://docs.aws.amazon.com/sns/latest/dg/SNSMobilePush.html>`_ . For more information about obtaining the PlatformPrincipal and PlatformCredential for each of the supported push notification services, see `Getting Started with Apple Push Notification Service <http://docs.aws.amazon.com/sns/latest/dg/mobile-push-apns.html>`_ , `Getting Started with Amazon Device Messaging <http://docs.aws.amazon.com/sns/latest/dg/mobile-push-adm.html>`_ , `Getting Started with Baidu Cloud Push <http://docs.aws.amazon.com/sns/latest/dg/mobile-push-baidu.html>`_ , `Getting Started with Google Cloud Messaging for Android <http://docs.aws.amazon.com/sns/latest/dg/mobile-push-gcm.html>`_ , `Getting Started with MPNS <http://docs.aws.amazon.com/sns/latest/dg/mobile-push-mpns.html>`_ , or `Getting Started with WNS <http://docs.aws.amazon.com/sns/latest/dg/mobile-push-wns.html>`_ . 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sns-2010-03-31/CreatePlatformApplication>`_


========
Synopsis
========

::

    create-platform-application
  --name <value>
  --platform <value>
  --attributes <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  Application names must be made up of only uppercase and lowercase ASCII letters, numbers, underscores, hyphens, and periods, and must be between 1 and 256 characters long.

  

``--platform`` (string)


  The following platforms are supported: ADM (Amazon Device Messaging), APNS (Apple Push Notification Service), APNS_SANDBOX, and GCM (Google Cloud Messaging).

  

``--attributes`` (map)


  For a list of attributes, see `set-platform-application-attributes <http://docs.aws.amazon.com/sns/latest/api/API_SetPlatformApplicationAttributes.html>`_  

  



Shorthand Syntax::

    KeyName1=string,KeyName2=string




JSON Syntax::

  {"string": "string"
    ...}



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

PlatformApplicationArn -> (string)

  

  PlatformApplicationArn is returned.

  

  

