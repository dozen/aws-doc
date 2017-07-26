[ :ref:`aws <cli:aws>` . :ref:`pinpoint <cli:aws pinpoint>` ]

.. _cli:aws pinpoint update-application-settings:


***************************
update-application-settings
***************************



===========
Description
===========

Used to update the settings for an app.

========
Synopsis
========

::

    update-application-settings
  --application-id <value>
  --write-application-settings-request <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--application-id`` (string)


``--write-application-settings-request`` (structure)
Creating application setting request



Shorthand Syntax::

    Limits={Daily=integer,Total=integer},QuietTime={End=string,Start=string}




JSON Syntax::

  {
    "Limits": {
      "Daily": integer,
      "Total": integer
    },
    "QuietTime": {
      "End": "string",
      "Start": "string"
    }
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ApplicationSettingsResource -> (structure)

  Application settings.

  ApplicationId -> (string)

    The unique ID for the application.

    

  LastModifiedDate -> (string)

    The date that the settings were last updated in ISO 8601 format.

    

  Limits -> (structure)

    The default campaign limits for the app. These limits apply to each campaign for the app, unless the campaign overrides the default with limits of its own.

    Daily -> (integer)

      The maximum number of messages that the campaign can send daily.

      

    Total -> (integer)

      The maximum total number of messages that the campaign can send.

      

    

  QuietTime -> (structure)

    The default quiet time for the app. Each campaign for this app sends no messages during this time unless the campaign overrides the default with a quiet time of its own.

    End -> (string)

      The default end time for quiet time in ISO 8601 format.

      

    Start -> (string)

      The default start time for quiet time in ISO 8601 format.

      

    

  

