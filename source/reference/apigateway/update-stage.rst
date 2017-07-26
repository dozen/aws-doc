[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway update-stage:


************
update-stage
************



===========
Description
===========



Changes information about a  Stage resource.



========
Synopsis
========

::

    update-stage
  --rest-api-id <value>
  --stage-name <value>
  [--patch-operations <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--rest-api-id`` (string)


  The identifier of the  RestApi resource for the  Stage resource to change information about.

  

``--stage-name`` (string)


  The name of the  Stage resource to change information about.

  

``--patch-operations`` (list)


  A list of operations describing the updates to apply to the specified resource. The patches are applied in the order specified in the list.

  



Shorthand Syntax::

    op=string,path=string,value=string,from=string ...




JSON Syntax::

  [
    {
      "op": "add"|"remove"|"replace"|"move"|"copy"|"test",
      "path": "string",
      "value": "string",
      "from": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

deploymentId -> (string)

  

  The identifier of the  Deployment that the stage points to.

  

  

clientCertificateId -> (string)

  

  

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

  

  A map that defines the method settings for a  Stage resource. Keys are defined as ``{resource_path}/{http_method}`` for an individual method override, or ``\*/\*`` for the settings applied to all methods in the stage.

  

  key -> (string)

    

    

  value -> (structure)

    

    Specifies the method setting properties.

    

    metricsEnabled -> (boolean)

      

      Specifies whether Amazon CloudWatch metrics are enabled for this method. The PATCH path for this setting is ``/{method_setting_key}/metrics/enabled`` , and the value is a Boolean.

      

      

    loggingLevel -> (string)

      

      Specifies the logging level for this method, which effects the log entries pushed to Amazon CloudWatch Logs. The PATCH path for this setting is ``/{method_setting_key}/logging/loglevel`` , and the available levels are ``OFF`` , ``ERROR`` , and ``INFO`` .

      

      

    dataTraceEnabled -> (boolean)

      

      Specifies the whether data trace logging is enabled for this method, which effects the log entries pushed to Amazon CloudWatch Logs. The PATCH path for this setting is ``/{method_setting_key}/logging/dataTrace`` , and the value is a Boolean.

      

      

    throttlingBurstLimit -> (integer)

      

      Specifies the throttling burst limit. The PATCH path for this setting is ``/{method_setting_key}/throttling/burstLimit`` , and the value is an integer.

      

      

    throttlingRateLimit -> (double)

      

      Specifies the throttling rate limit. The PATCH path for this setting is ``/{method_setting_key}/throttling/rateLimit`` , and the value is a double.

      

      

    cachingEnabled -> (boolean)

      

      Specifies whether responses should be cached and returned for requests. A cache cluster must be enabled on the stage for responses to be cached. The PATCH path for this setting is ``/{method_setting_key}/caching/enabled`` , and the value is a Boolean.

      

      

    cacheTtlInSeconds -> (integer)

      

      Specifies the time to live (TTL) in seconds, for cached responses. The higher a the TTL, the longer the response will be cached. The PATCH path for this setting is ``/{method_setting_key}/caching/ttlInSeconds`` , and the value is an integer.

      

      

    cacheDataEncrypted -> (boolean)

      

      Specifies whether the cached responses are encrypted. The PATCH path for this setting is ``/{method_setting_key}/caching/dataEncrypted`` , and the value is a Boolean.

      

      

    

  

variables -> (map)

  

  A map that defines the stage variables for a  Stage resource. Variable names can have alphanumeric characters, and the values must match ``[A-Za-z0-9-._~:/?#=,]+`` .

  

  key -> (string)

    

    

  value -> (string)

    

    

  

createdDate -> (timestamp)

  

  The date and time that the stage was created, in `ISO 8601 format`_ .

  

  

lastUpdatedDate -> (timestamp)

  

  The date and time that information about the stage was last updated, in `ISO 8601 format`_ .

  

  



.. _ISO 8601 format: http://www.iso.org/iso/home/standards/iso8601.htm
