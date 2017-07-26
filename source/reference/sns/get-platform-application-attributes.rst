[ :ref:`aws <cli:aws>` . :ref:`sns <cli:aws sns>` ]

.. _cli:aws sns get-platform-application-attributes:


***********************************
get-platform-application-attributes
***********************************



===========
Description
===========



Retrieves the attributes of the platform application object for the supported push notification services, such as APNS and GCM. For more information, see `Using Amazon SNS Mobile Push Notifications <http://docs.aws.amazon.com/sns/latest/dg/SNSMobilePush.html>`_ . 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sns-2010-03-31/GetPlatformApplicationAttributes>`_


========
Synopsis
========

::

    get-platform-application-attributes
  --platform-application-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--platform-application-arn`` (string)


  PlatformApplicationArn for GetPlatformApplicationAttributesInput.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Attributes -> (map)

  

  Attributes include the following:

   

   
  * ``EventEndpointCreated`` -- Topic ARN to which EndpointCreated event notifications should be sent. 
   
  * ``EventEndpointDeleted`` -- Topic ARN to which EndpointDeleted event notifications should be sent. 
   
  * ``EventEndpointUpdated`` -- Topic ARN to which EndpointUpdate event notifications should be sent. 
   
  * ``EventDeliveryFailure`` -- Topic ARN to which DeliveryFailure event notifications should be sent upon Direct publish delivery failure (permanent) to one of the application's endpoints. 
   

  

  key -> (string)

    

    

  value -> (string)

    

    

  

