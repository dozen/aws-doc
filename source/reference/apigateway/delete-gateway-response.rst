[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway delete-gateway-response:


***********************
delete-gateway-response
***********************



===========
Description
===========



Clears any customization of a  GatewayResponse of a specified response type on the given  RestApi and resets it with the default settings.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/DeleteGatewayResponse>`_


========
Synopsis
========

::

    delete-gateway-response
  --rest-api-id <value>
  --response-type <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rest-api-id`` (string)


  The string identifier of the associated  RestApi .

  

``--response-type`` (string)


  

  The response type of the associated  GatewayResponse . Valid values are 

  
  * ACCESS_DENIED
  
  * API_CONFIGURATION_ERROR
  
  * AUTHORIZER_FAILURE
  
  * AUTHORIZER_CONFIGURATION_ERROR
  
  * BAD_REQUEST_PARAMETERS
  
  * BAD_REQUEST_BODY
  
  * DEFAULT_4XX
  
  * DEFAULT_5XX
  
  * EXPIRED_TOKEN
  
  * INVALID_SIGNATURE
  
  * INTEGRATION_FAILURE
  
  * INTEGRATION_TIMEOUT
  
  * INVALID_API_KEY
  
  * MISSING_AUTHENTICATION_TOKEN
  
  * QUOTA_EXCEEDED
  
  * REQUEST_TOO_LARGE
  
  * RESOURCE_NOT_FOUND
  
  * THROTTLED
  
  * UNAUTHORIZED
  
  * UNSUPPORTED_MEDIA_TYPES
  

   

  

  

  Possible values:

  
  *   ``DEFAULT_4XX``

  
  *   ``DEFAULT_5XX``

  
  *   ``RESOURCE_NOT_FOUND``

  
  *   ``UNAUTHORIZED``

  
  *   ``INVALID_API_KEY``

  
  *   ``ACCESS_DENIED``

  
  *   ``AUTHORIZER_FAILURE``

  
  *   ``AUTHORIZER_CONFIGURATION_ERROR``

  
  *   ``INVALID_SIGNATURE``

  
  *   ``EXPIRED_TOKEN``

  
  *   ``MISSING_AUTHENTICATION_TOKEN``

  
  *   ``INTEGRATION_FAILURE``

  
  *   ``INTEGRATION_TIMEOUT``

  
  *   ``API_CONFIGURATION_ERROR``

  
  *   ``UNSUPPORTED_MEDIA_TYPE``

  
  *   ``BAD_REQUEST_PARAMETERS``

  
  *   ``BAD_REQUEST_BODY``

  
  *   ``REQUEST_TOO_LARGE``

  
  *   ``THROTTLED``

  
  *   ``QUOTA_EXCEEDED``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None