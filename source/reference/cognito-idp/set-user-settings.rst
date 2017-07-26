[ :ref:`aws <cli:aws>` . :ref:`cognito-idp <cli:aws cognito-idp>` ]

.. _cli:aws cognito-idp set-user-settings:


*****************
set-user-settings
*****************



===========
Description
===========



Sets the user settings like multi-factor authentication (MFA). If MFA is to be removed for a particular attribute pass the attribute with code delivery as null. If null list is passed, all MFA options are removed.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-idp-2016-04-18/SetUserSettings>`_


========
Synopsis
========

::

    set-user-settings
  --access-token <value>
  --mfa-options <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--access-token`` (string)


  The access token for the set user settings request.

  

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

