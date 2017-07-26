[ :ref:`aws <cli:aws>` . :ref:`cognito-idp <cli:aws cognito-idp>` ]

.. _cli:aws cognito-idp admin-set-user-settings:


***********************
admin-set-user-settings
***********************



===========
Description
===========



Sets all the user settings for a specified user name. Works on any user.

 

Requires developer credentials.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-idp-2016-04-18/AdminSetUserSettings>`_


========
Synopsis
========

::

    admin-set-user-settings
  --user-pool-id <value>
  --username <value>
  --mfa-options <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--user-pool-id`` (string)


  The user pool ID for the user pool where you want to set the user's settings, such as MFA options.

  

``--username`` (string)


  The user name of the user for whom you wish to set user settings.

  

``--mfa-options`` (list)


  Specifies the options for MFA (e.g., email or phone number).

  



Shorthand Syntax::

    DeliveryMedium=string,AttributeName=string ...




JSON Syntax::

  [
    {
      "DeliveryMedium": "SMS"|"EMAIL",
      "AttributeName": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

