[ :ref:`aws <cli:aws>` . :ref:`cognito-idp <cli:aws cognito-idp>` ]

.. _cli:aws cognito-idp confirm-sign-up:


***************
confirm-sign-up
***************



===========
Description
===========



Confirms registration of a user and handles the existing alias from a previous user.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-idp-2016-04-18/ConfirmSignUp>`_


========
Synopsis
========

::

    confirm-sign-up
  --client-id <value>
  [--secret-hash <value>]
  --username <value>
  --confirmation-code <value>
  [--force-alias-creation | --no-force-alias-creation]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--client-id`` (string)


  The ID of the client associated with the user pool.

  

``--secret-hash`` (string)


  A keyed-hash message authentication code (HMAC) calculated using the secret key of a user pool client and username plus the client ID in the message.

  

``--username`` (string)


  The user name of the user whose registration you wish to confirm.

  

``--confirmation-code`` (string)


  The confirmation code sent by a user's request to confirm registration.

  

``--force-alias-creation`` | ``--no-force-alias-creation`` (boolean)


  Boolean to be specified to force user confirmation irrespective of existing alias. By default set to ``False`` . If this parameter is set to ``True`` and the phone number/email used for sign up confirmation already exists as an alias with a different user, the API call will migrate the alias from the previous user to the newly created user being confirmed. If set to ``False`` , the API will throw an **AliasExistsException** error.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

