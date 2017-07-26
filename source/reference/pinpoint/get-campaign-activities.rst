[ :ref:`aws <cli:aws>` . :ref:`pinpoint <cli:aws pinpoint>` ]

.. _cli:aws pinpoint get-campaign-activities:


***********************
get-campaign-activities
***********************



===========
Description
===========

Returns information about the activity performed by a campaign.

========
Synopsis
========

::

    get-campaign-activities
  --application-id <value>
  --campaign-id <value>
  [--page-size <value>]
  [--token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-id`` (string)


``--campaign-id`` (string)


``--page-size`` (string)


``--token`` (string)


``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ActivitiesResponse -> (structure)

  Activities for campaign.

  Item -> (list)

    List of campaign activities

    (structure)

      Activity definition

      ApplicationId -> (string)

        The ID of the application to which the campaign applies.

        

      CampaignId -> (string)

        The ID of the campaign to which the activity applies.

        

      End -> (string)

        The actual time the activity was marked CANCELLED or COMPLETED. Provided in ISO 8601 format.

        

      Id -> (string)

        The unique activity ID.

        

      Result -> (string)

        Indicates whether the activity succeeded. Valid values: SUCCESS, FAIL

        

      ScheduledStart -> (string)

        The scheduled start time for the activity in ISO 8601 format.

        

      Start -> (string)

        The actual start time of the activity in ISO 8601 format.

        

      State -> (string)

        The state of the activity. Valid values: PENDING, INITIALIZING, RUNNING, PAUSED, CANCELLED, COMPLETED

        

      SuccessfulEndpointCount -> (integer)

        The total number of endpoints to which the campaign successfully delivered messages.

        

      TimezonesCompletedCount -> (integer)

        The total number of timezones completed.

        

      TimezonesTotalCount -> (integer)

        The total number of unique timezones present in the segment.

        

      TotalEndpointCount -> (integer)

        The total number of endpoints to which the campaign attempts to deliver messages.

        

      TreatmentId -> (string)

        The ID of a variation of the campaign used for A/B testing.

        

      

    

  

