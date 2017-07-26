[ :ref:`aws <cli:aws>` . :ref:`pinpoint <cli:aws pinpoint>` ]

.. _cli:aws pinpoint get-campaign-version:


********************
get-campaign-version
********************



===========
Description
===========

Returns information about a specific version of a campaign.

========
Synopsis
========

::

    get-campaign-version
  --application-id <value>
  --campaign-id <value>
  --campaign-version <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-id`` (string)


``--campaign-id`` (string)


``--campaign-version`` (string)


``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

CampaignResponse -> (structure)

  Campaign definition

  AdditionalTreatments -> (list)

    Treatments that are defined in addition to the default treatment.

    (structure)

      Treatment resource

      Id -> (string)

        The unique treatment ID.

        

      MessageConfiguration -> (structure)

        The message configuration settings.

        APNSMessage -> (structure)

          The message that the campaign delivers to APNS channels. Overrides the default message.

          Action -> (string)

            The action that occurs if the user taps a push notification delivered by the campaign: OPEN_APP - Your app launches, or it becomes the foreground app if it has been sent to the background. This is the default action. DEEP_LINK - Uses deep linking features in iOS and Android to open your app and display a designated user interface within the app. URL - The default mobile browser on the user's device launches and opens a web page at the URL you specify.

            

          Body -> (string)

            The message body. Can include up to 140 characters.

            

          ImageIconUrl -> (string)

            The URL that points to the icon image for the push notification icon, for example, the app icon.

            

          ImageSmallIconUrl -> (string)

            The URL that points to the small icon image for the push notification icon, for example, the app icon.

            

          ImageUrl -> (string)

            The URL that points to an image used in the push notification.

            

          JsonBody -> (string)

            The JSON payload used for a silent push.

            

          MediaUrl -> (string)

            The URL that points to the media resource, for example a .mp4 or .gif file.

            

          SilentPush -> (boolean)

            Indicates if the message should display on the users device. Silent pushes can be used for Remote Configuration and Phone Home use cases. 

            

          Title -> (string)

            The message title that displays above the message on the user's device.

            

          Url -> (string)

            The URL to open in the user's mobile browser. Used if the value for Action is URL.

            

          

        DefaultMessage -> (structure)

          The default message for all channels.

          Action -> (string)

            The action that occurs if the user taps a push notification delivered by the campaign: OPEN_APP - Your app launches, or it becomes the foreground app if it has been sent to the background. This is the default action. DEEP_LINK - Uses deep linking features in iOS and Android to open your app and display a designated user interface within the app. URL - The default mobile browser on the user's device launches and opens a web page at the URL you specify.

            

          Body -> (string)

            The message body. Can include up to 140 characters.

            

          ImageIconUrl -> (string)

            The URL that points to the icon image for the push notification icon, for example, the app icon.

            

          ImageSmallIconUrl -> (string)

            The URL that points to the small icon image for the push notification icon, for example, the app icon.

            

          ImageUrl -> (string)

            The URL that points to an image used in the push notification.

            

          JsonBody -> (string)

            The JSON payload used for a silent push.

            

          MediaUrl -> (string)

            The URL that points to the media resource, for example a .mp4 or .gif file.

            

          SilentPush -> (boolean)

            Indicates if the message should display on the users device. Silent pushes can be used for Remote Configuration and Phone Home use cases. 

            

          Title -> (string)

            The message title that displays above the message on the user's device.

            

          Url -> (string)

            The URL to open in the user's mobile browser. Used if the value for Action is URL.

            

          

        EmailMessage -> (structure)

          The email message configuration.

          Body -> (string)

            The email text body.

            

          HtmlBody -> (string)

            The email html body.

            

          Title -> (string)

            The email title (Or subject).

            

          

        GCMMessage -> (structure)

          The message that the campaign delivers to GCM channels. Overrides the default message.

          Action -> (string)

            The action that occurs if the user taps a push notification delivered by the campaign: OPEN_APP - Your app launches, or it becomes the foreground app if it has been sent to the background. This is the default action. DEEP_LINK - Uses deep linking features in iOS and Android to open your app and display a designated user interface within the app. URL - The default mobile browser on the user's device launches and opens a web page at the URL you specify.

            

          Body -> (string)

            The message body. Can include up to 140 characters.

            

          ImageIconUrl -> (string)

            The URL that points to the icon image for the push notification icon, for example, the app icon.

            

          ImageSmallIconUrl -> (string)

            The URL that points to the small icon image for the push notification icon, for example, the app icon.

            

          ImageUrl -> (string)

            The URL that points to an image used in the push notification.

            

          JsonBody -> (string)

            The JSON payload used for a silent push.

            

          MediaUrl -> (string)

            The URL that points to the media resource, for example a .mp4 or .gif file.

            

          SilentPush -> (boolean)

            Indicates if the message should display on the users device. Silent pushes can be used for Remote Configuration and Phone Home use cases. 

            

          Title -> (string)

            The message title that displays above the message on the user's device.

            

          Url -> (string)

            The URL to open in the user's mobile browser. Used if the value for Action is URL.

            

          

        SMSMessage -> (structure)

          The SMS message configuration.

          Body -> (string)

            The SMS text body.

            

          MessageType -> (string)

            Is this is a transactional SMS message, otherwise a promotional message.

            

          SenderId -> (string)

            Sender ID of sent message.

            

          

        

      Schedule -> (structure)

        The campaign schedule.

        EndTime -> (string)

          The scheduled time that the campaign ends in ISO 8601 format.

          

        Frequency -> (string)

          How often the campaign delivers messages. Valid values: ONCE, HOURLY, DAILY, WEEKLY, MONTHLY

          

        IsLocalTime -> (boolean)

          Indicates whether the campaign schedule takes effect according to each user's local time.

          

        QuietTime -> (structure)

          The time during which the campaign sends no messages.

          End -> (string)

            The default end time for quiet time in ISO 8601 format.

            

          Start -> (string)

            The default start time for quiet time in ISO 8601 format.

            

          

        StartTime -> (string)

          The scheduled time that the campaign begins in ISO 8601 format.

          

        Timezone -> (string)

          The starting UTC offset for the schedule if the value for isLocalTime is true Valid values: UTC UTC+01 UTC+02 UTC+03 UTC+03:30 UTC+04 UTC+04:30 UTC+05 UTC+05:30 UTC+05:45 UTC+06 UTC+06:30 UTC+07 UTC+08 UTC+09 UTC+09:30 UTC+10 UTC+10:30 UTC+11 UTC+12 UTC+13 UTC-02 UTC-03 UTC-04 UTC-05 UTC-06 UTC-07 UTC-08 UTC-09 UTC-10 UTC-11

          

        

      SizePercent -> (integer)

        The allocated percentage of users for this treatment.

        

      State -> (structure)

        The treatment status.

        CampaignStatus -> (string)

          The status of the campaign, or the status of a treatment that belongs to an A/B test campaign. Valid values: SCHEDULED, EXECUTING, PENDING_NEXT_RUN, COMPLETED, PAUSED

          

        

      TreatmentDescription -> (string)

        A custom description for the treatment.

        

      TreatmentName -> (string)

        The custom name of a variation of the campaign used for A/B testing.

        

      

    

  ApplicationId -> (string)

    The ID of the application to which the campaign applies.

    

  CreationDate -> (string)

    The date the campaign was created in ISO 8601 format.

    

  DefaultState -> (structure)

    The status of the campaign's default treatment. Only present for A/B test campaigns.

    CampaignStatus -> (string)

      The status of the campaign, or the status of a treatment that belongs to an A/B test campaign. Valid values: SCHEDULED, EXECUTING, PENDING_NEXT_RUN, COMPLETED, PAUSED

      

    

  Description -> (string)

    A description of the campaign.

    

  HoldoutPercent -> (integer)

    The allocated percentage of end users who will not receive messages from this campaign.

    

  Id -> (string)

    The unique campaign ID.

    

  IsPaused -> (boolean)

    Indicates whether the campaign is paused. A paused campaign does not send messages unless you resume it by setting IsPaused to false.

    

  LastModifiedDate -> (string)

    The date the campaign was last updated in ISO 8601 format. 

    

  Limits -> (structure)

    The campaign limits settings.

    Daily -> (integer)

      The maximum number of messages that the campaign can send daily.

      

    Total -> (integer)

      The maximum total number of messages that the campaign can send.

      

    

  MessageConfiguration -> (structure)

    The message configuration settings.

    APNSMessage -> (structure)

      The message that the campaign delivers to APNS channels. Overrides the default message.

      Action -> (string)

        The action that occurs if the user taps a push notification delivered by the campaign: OPEN_APP - Your app launches, or it becomes the foreground app if it has been sent to the background. This is the default action. DEEP_LINK - Uses deep linking features in iOS and Android to open your app and display a designated user interface within the app. URL - The default mobile browser on the user's device launches and opens a web page at the URL you specify.

        

      Body -> (string)

        The message body. Can include up to 140 characters.

        

      ImageIconUrl -> (string)

        The URL that points to the icon image for the push notification icon, for example, the app icon.

        

      ImageSmallIconUrl -> (string)

        The URL that points to the small icon image for the push notification icon, for example, the app icon.

        

      ImageUrl -> (string)

        The URL that points to an image used in the push notification.

        

      JsonBody -> (string)

        The JSON payload used for a silent push.

        

      MediaUrl -> (string)

        The URL that points to the media resource, for example a .mp4 or .gif file.

        

      SilentPush -> (boolean)

        Indicates if the message should display on the users device. Silent pushes can be used for Remote Configuration and Phone Home use cases. 

        

      Title -> (string)

        The message title that displays above the message on the user's device.

        

      Url -> (string)

        The URL to open in the user's mobile browser. Used if the value for Action is URL.

        

      

    DefaultMessage -> (structure)

      The default message for all channels.

      Action -> (string)

        The action that occurs if the user taps a push notification delivered by the campaign: OPEN_APP - Your app launches, or it becomes the foreground app if it has been sent to the background. This is the default action. DEEP_LINK - Uses deep linking features in iOS and Android to open your app and display a designated user interface within the app. URL - The default mobile browser on the user's device launches and opens a web page at the URL you specify.

        

      Body -> (string)

        The message body. Can include up to 140 characters.

        

      ImageIconUrl -> (string)

        The URL that points to the icon image for the push notification icon, for example, the app icon.

        

      ImageSmallIconUrl -> (string)

        The URL that points to the small icon image for the push notification icon, for example, the app icon.

        

      ImageUrl -> (string)

        The URL that points to an image used in the push notification.

        

      JsonBody -> (string)

        The JSON payload used for a silent push.

        

      MediaUrl -> (string)

        The URL that points to the media resource, for example a .mp4 or .gif file.

        

      SilentPush -> (boolean)

        Indicates if the message should display on the users device. Silent pushes can be used for Remote Configuration and Phone Home use cases. 

        

      Title -> (string)

        The message title that displays above the message on the user's device.

        

      Url -> (string)

        The URL to open in the user's mobile browser. Used if the value for Action is URL.

        

      

    EmailMessage -> (structure)

      The email message configuration.

      Body -> (string)

        The email text body.

        

      HtmlBody -> (string)

        The email html body.

        

      Title -> (string)

        The email title (Or subject).

        

      

    GCMMessage -> (structure)

      The message that the campaign delivers to GCM channels. Overrides the default message.

      Action -> (string)

        The action that occurs if the user taps a push notification delivered by the campaign: OPEN_APP - Your app launches, or it becomes the foreground app if it has been sent to the background. This is the default action. DEEP_LINK - Uses deep linking features in iOS and Android to open your app and display a designated user interface within the app. URL - The default mobile browser on the user's device launches and opens a web page at the URL you specify.

        

      Body -> (string)

        The message body. Can include up to 140 characters.

        

      ImageIconUrl -> (string)

        The URL that points to the icon image for the push notification icon, for example, the app icon.

        

      ImageSmallIconUrl -> (string)

        The URL that points to the small icon image for the push notification icon, for example, the app icon.

        

      ImageUrl -> (string)

        The URL that points to an image used in the push notification.

        

      JsonBody -> (string)

        The JSON payload used for a silent push.

        

      MediaUrl -> (string)

        The URL that points to the media resource, for example a .mp4 or .gif file.

        

      SilentPush -> (boolean)

        Indicates if the message should display on the users device. Silent pushes can be used for Remote Configuration and Phone Home use cases. 

        

      Title -> (string)

        The message title that displays above the message on the user's device.

        

      Url -> (string)

        The URL to open in the user's mobile browser. Used if the value for Action is URL.

        

      

    SMSMessage -> (structure)

      The SMS message configuration.

      Body -> (string)

        The SMS text body.

        

      MessageType -> (string)

        Is this is a transactional SMS message, otherwise a promotional message.

        

      SenderId -> (string)

        Sender ID of sent message.

        

      

    

  Name -> (string)

    The custom name of the campaign.

    

  Schedule -> (structure)

    The campaign schedule.

    EndTime -> (string)

      The scheduled time that the campaign ends in ISO 8601 format.

      

    Frequency -> (string)

      How often the campaign delivers messages. Valid values: ONCE, HOURLY, DAILY, WEEKLY, MONTHLY

      

    IsLocalTime -> (boolean)

      Indicates whether the campaign schedule takes effect according to each user's local time.

      

    QuietTime -> (structure)

      The time during which the campaign sends no messages.

      End -> (string)

        The default end time for quiet time in ISO 8601 format.

        

      Start -> (string)

        The default start time for quiet time in ISO 8601 format.

        

      

    StartTime -> (string)

      The scheduled time that the campaign begins in ISO 8601 format.

      

    Timezone -> (string)

      The starting UTC offset for the schedule if the value for isLocalTime is true Valid values: UTC UTC+01 UTC+02 UTC+03 UTC+03:30 UTC+04 UTC+04:30 UTC+05 UTC+05:30 UTC+05:45 UTC+06 UTC+06:30 UTC+07 UTC+08 UTC+09 UTC+09:30 UTC+10 UTC+10:30 UTC+11 UTC+12 UTC+13 UTC-02 UTC-03 UTC-04 UTC-05 UTC-06 UTC-07 UTC-08 UTC-09 UTC-10 UTC-11

      

    

  SegmentId -> (string)

    The ID of the segment to which the campaign sends messages.

    

  SegmentVersion -> (integer)

    The version of the segment to which the campaign sends messages.

    

  State -> (structure)

    The campaign status. An A/B test campaign will have a status of COMPLETED only when all treatments have a status of COMPLETED.

    CampaignStatus -> (string)

      The status of the campaign, or the status of a treatment that belongs to an A/B test campaign. Valid values: SCHEDULED, EXECUTING, PENDING_NEXT_RUN, COMPLETED, PAUSED

      

    

  TreatmentDescription -> (string)

    A custom description for the treatment.

    

  TreatmentName -> (string)

    The custom name of a variation of the campaign used for A/B testing.

    

  Version -> (integer)

    The campaign version number.

    

  

