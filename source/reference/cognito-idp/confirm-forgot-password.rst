[ :ref:`aws <cli:aws>` . :ref:`cognito-idp <cli:aws cognito-idp>` ]

.. _cli:aws cognito-idp confirm-forgot-password:


***********************
confirm-forgot-password
***********************



===========
Description
===========



Allows a user to enter a confirmation code to reset a forgotten password.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-idp-2016-04-18/ConfirmForgotPassword>`_


========
Synopsis
========

::

    confirm-forgot-password
  --client-id <value>
  [--secret-hash <value>]
  --username <value>
  --confirmation-code <value>
  --password <value>
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


  The user name of the user for whom you want to enter a code to retrieve a forgotten password.

  

``--confirmation-code`` (string)


  The confirmation code sent by a user's request to retrieve a forgotten password. For more information, see `forgot-password <API_ForgotPassword.html>`_  

  

``--password`` (string)


  The password sent by a user's request to retrieve a forgotten password.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

