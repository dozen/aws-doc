[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway get-stages:


**********
get-stages
**********



===========
Description
===========



Gets information about one or more  Stage resources.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/GetStages>`_


========
Synopsis
========

::

    get-stages
  --rest-api-id <value>
  [--deployment-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rest-api-id`` (string)


  The string identifier of the associated  RestApi .

  

``--deployment-id`` (string)


  The stages' deployment identifiers.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get the list of stages for a REST API**

Command::

  aws apigateway get-stages --rest-api-id 1234123412

Output::

  {
      "item": [
          {
              "stageName": "dev", 
              "cacheClusterSize": "0.5", 
              "cacheClusterEnabled": true, 
              "cacheClusterStatus": "AVAILABLE", 
              "deploymentId": "123h64", 
              "lastUpdatedDate": 1456185138, 
              "createdDate": 1453589092, 
              "methodSettings": {
                  "~1resource~1subresource/POST": {
                      "cacheTtlInSeconds": 300, 
                      "loggingLevel": "INFO", 
                      "dataTraceEnabled": true, 
                      "metricsEnabled": true, 
                      "throttlingRateLimit": 500.0, 
                      "cacheDataEncrypted": false, 
                      "cachingEnabled": false, 
                      "throttlingBurstLimit": 1000
                  }
              }
          }
      ]
  }


======
Output
======

item -> (list)

  

  The current page of elements from this collection.

  

  (structure)

    

    Represents a unique identifier for a version of a deployed  RestApi that is callable by users.

      `Deploy an API <http://docs.aws.amazon.com/apigateway/latest/developerguide/how-to-deploy-api.html>`_  

    deploymentId -> (string)

      

      The identifier of the  Deployment that the stage points to.

      

      

    clientCertificateId -> (string)

      

      The identifier of a client certificate for an API stage.

      

      

    stageName -> (string)

      

      The name of the stage is the first path segment in the Uniform Resource Identifier (URI) of a call to Amazon API Gateway.

      

      

    description -> (string)

      

      The stage's description.

      

      

    cacheClusterEnabled -> (boolean)

      

      Specifies whether a cache cluster is enabled for the stage.

      

      

    cacheClusterSize -> (string)

      

      The size of the cache cluster for the stage, if enabled.

      

      

    cacheClusterStatus -> (string)

      

      The status of the cache cluster for the stage, if enabled.

      

      

    methodSettings -> (map)

      

      A map that defines the method settings for a  Stage resource. Keys (designated as ``/{method_setting_key`` below) are method paths defined as ``{resource_path}/{http_method}`` for an individual method override, or ``/\*/\*`` for overriding all methods in the stage. 

      

      key -> (string)

        

        

      value -> (structure)

        

        Specifies the method setting properties.

        

        metricsEnabled -> (boolean)

          

          Specifies whether Amazon CloudWatch metrics are enabled for this method. The PATCH path for this setting is ``/{method_setting_key}/metrics/enabled`` , and the value is a Boolean.

          

          

        loggingLevel -> (string)

          

          Specifies the logging level for this method, which effects the log entries pushed to Amazon CloudWatch Logs. The PATCH path for this setting is ``/{method_setting_key}/logging/loglevel`` , and the available levels are ``OFF`` , ``ERROR`` , and ``INFO`` .

          

          

        dataTraceEnabled -> (boolean)

          

          Specifies whether data trace logging is enabled for this method, which effects the log entries pushed to Amazon CloudWatch Logs. The PATCH path for this setting is ``/{method_setting_key}/logging/dataTrace`` , and the value is a Boolean.

          

          

        throttlingBurstLimit -> (integer)

          

          Specifies the throttling burst limit. The PATCH path for this setting is ``/{method_setting_key}/throttling/burstLimit`` , and the value is an integer.

          

          

        throttlingRateLimit -> (double)

          

          Specifies the throttling rate limit. The PATCH path for this setting is ``/{method_setting_key}/throttling/rateLimit`` , and the value is a double.

          

          

        cachingEnabled -> (boolean)

          

          Specifies whether responses should be cached and returned for requests. A cache cluster must be enabled on the stage for responses to be cached. The PATCH path for this setting is ``/{method_setting_key}/caching/enabled`` , and the value is a Boolean.

          

          

        cacheTtlInSeconds -> (integer)

          

          Specifies the time to live (TTL), in seconds, for cached responses. The higher the TTL, the longer the response will be cached. The PATCH path for this setting is ``/{method_setting_key}/caching/ttlInSeconds`` , and the value is an integer.

          

          

        cacheDataEncrypted -> (boolean)

          

          Specifies whether the cached responses are encrypted. The PATCH path for this setting is ``/{method_setting_key}/caching/dataEncrypted`` , and the value is a Boolean.

          

          

        requireAuthorizationForCacheControl -> (boolean)

          

          Specifies whether authorization is required for a cache invalidation request. The PATCH path for this setting is ``/{method_setting_key}/caching/requireAuthorizationForCacheControl`` , and the value is a Boolean.

          

          

        unauthorizedCacheControlHeaderStrategy -> (string)

          

          Specifies how to handle unauthorized requests for cache invalidation. The PATCH path for this setting is ``/{method_setting_key}/caching/unauthorizedCacheControlHeaderStrategy`` , and the available values are ``FAIL_WITH_403`` , ``SUCCEED_WITH_RESPONSE_HEADER`` , ``SUCCEED_WITHOUT_RESPONSE_HEADER`` .

          

          

        

      

    variables -> (map)

      

      A map that defines the stage variables for a  Stage resource. Variable names can have alphanumeric and underscore characters, and the values must match ``[A-Za-z0-9-._~:/?#=,]+`` .

      

      key -> (string)

        

        

      value -> (string)

        

        

      

    documentationVersion -> (string)

      

      The version of the associated API documentation.

      

      

    createdDate -> (timestamp)

      

      The timestamp when the stage was created.

      

      

    lastUpdatedDate -> (timestamp)

      

      The timestamp when the stage last updated.

      

      

    

  

