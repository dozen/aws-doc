[ :ref:`aws <cli:aws>` . :ref:`sns <cli:aws sns>` ]

.. _cli:aws sns set-platform-application-attributes:


***********************************
set-platform-application-attributes
***********************************



===========
Description
===========



Sets the attributes of the platform application object for the supported push notification services, such as APNS and GCM. For more information, see `Using Amazon SNS Mobile Push Notifications`_ . 



========
Synopsis
========

::

    set-platform-application-attributes
  --platform-application-arn <value>
  --attributes <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--platform-application-arn`` (string)


  PlatformApplicationArn for set-platform-application-attributes action.

  

``--attributes`` (map)


  A map of the platform application attributes. Attributes in this map include the following:

   

   
  * ``PlatformCredential`` -- The credential received from the notification service. For APNS/APNS_SANDBOX, PlatformCredential is "private key". For GCM, PlatformCredential is "API key". For ADM, PlatformCredential is "client secret".
   
  * ``PlatformPrincipal`` -- The principal received from the notification service. For APNS/APNS_SANDBOX, PlatformPrincipal is "SSL certificate". For GCM, PlatformPrincipal is not applicable. For ADM, PlatformPrincipal is "client id".
   
  * ``EventEndpointCreated`` -- Topic ARN to which EndpointCreated event notifications should be sent.
   
  * ``EventEndpointDeleted`` -- Topic ARN to which EndpointDeleted event notifications should be sent.
   
  * ``EventEndpointUpdated`` -- Topic ARN to which EndpointUpdate event notifications should be sent.
   
  * ``EventDeliveryFailure`` -- Topic ARN to which DeliveryFailure event notifications should be sent upon Direct publish delivery failure (permanent) to one of the application's endpoints.
   

  



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

None

.. _Using Amazon SNS Mobile Push Notifications: http://docs.aws.amazon.com/sns/latest/dg/SNSMobilePush.html
