[ :ref:`aws <cli:aws>` . :ref:`pinpoint <cli:aws pinpoint>` ]

.. _cli:aws pinpoint get-endpoint:


************
get-endpoint
************



===========
Description
===========

Returns information about an endpoint.

========
Synopsis
========

::

    get-endpoint
  --application-id <value>
  --endpoint-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-id`` (string)


``--endpoint-id`` (string)


``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

EndpointResponse -> (structure)

  Endpoint response

  Address -> (string)

    The address or token of the endpoint as provided by your push provider (e.g. DeviceToken or RegistrationId).

    

  ApplicationId -> (string)

    The ID of the application associated with the endpoint.

    

  Attributes -> (map)

    Custom attributes that your app reports to Amazon Pinpoint. You can use these attributes as selection criteria when you create a segment.

    key -> (string)

      

      

    value -> (list)

      

      (string)

        

        

      

    

  ChannelType -> (string)

    The channel type. Valid values: APNS, GCM

    

  CohortId -> (string)

    A number from 0 - 99 that represents the cohort the endpoint is assigned to. Endpoints are grouped into cohorts randomly, and each cohort contains approximately 1 percent of the endpoints for an app. Amazon Pinpoint assigns cohorts to the holdout or treatment allocations for a campaign.

    

  CreationDate -> (string)

    The last time the endpoint was created. Provided in ISO 8601 format.

    

  Demographic -> (structure)

    The endpoint demographic attributes.

    AppVersion -> (string)

      The version of the application associated with the endpoint.

      

    Locale -> (string)

      The endpoint locale in the following format: The ISO 639-1 alpha-2 code, followed by an underscore, followed by an ISO 3166-1 alpha-2 value. 

      

    Make -> (string)

      The endpoint make, such as such as Apple or Samsung.

      

    Model -> (string)

      The endpoint model, such as iPhone.

      

    ModelVersion -> (string)

      The endpoint model version.

      

    Platform -> (string)

      The endpoint platform, such as ios or android.

      

    PlatformVersion -> (string)

      The endpoint platform version.

      

    Timezone -> (string)

      The timezone of the endpoint. Specified as a tz database value, such as Americas/Los_Angeles.

      

    

  EffectiveDate -> (string)

    The last time the endpoint was updated. Provided in ISO 8601 format.

    

  EndpointStatus -> (string)

    The endpoint status. Can be either ACTIVE or INACTIVE. Will be set to INACTIVE if a delivery fails. Will be set to ACTIVE if the address is updated.

    

  Id -> (string)

    The unique ID that you assigned to the endpoint. The ID should be a globally unique identifier (GUID) to ensure that it is unique compared to all other endpoints for the application.

    

  Location -> (structure)

    The endpoint location attributes.

    City -> (string)

      The city where the endpoint is located.

      

    Country -> (string)

      Country according to ISO 3166-1 Alpha-2 codes. For example, US.

      

    Latitude -> (double)

      The latitude of the endpoint location. Rounded to one decimal (Roughly corresponding to a mile).

      

    Longitude -> (double)

      The longitude of the endpoint location. Rounded to one decimal (Roughly corresponding to a mile).

      

    PostalCode -> (string)

      The postal code or zip code of the endpoint.

      

    Region -> (string)

      The region of the endpoint location. For example, corresponds to a state in US.

      

    

  Metrics -> (map)

    Custom metrics that your app reports to Amazon Pinpoint.

    key -> (string)

      

      

    value -> (double)

      

      

    

  OptOut -> (string)

    Indicates whether a user has opted out of receiving messages with one of the following values: ALL – User receives all messages. NONE – User receives no messages.

    

  RequestId -> (string)

    The unique ID for the most recent request to update the endpoint.

    

  User -> (structure)

    Custom user-specific attributes that your app reports to Amazon Pinpoint.

    UserAttributes -> (map)

      Custom attributes specific to the user.

      key -> (string)

        

        

      value -> (list)

        

        (string)

          

          

        

      

    UserId -> (string)

      The unique ID of the user.

      

    

  ShardId -> (string)

    The ShardId of endpoint

    

  

