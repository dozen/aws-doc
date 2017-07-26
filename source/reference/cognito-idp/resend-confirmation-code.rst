[ :ref:`aws <cli:aws>` . :ref:`cognito-idp <cli:aws cognito-idp>` ]

.. _cli:aws cognito-idp resend-confirmation-code:


************************
resend-confirmation-code
************************



===========
Description
===========



Resends the confirmation (for confirmation of registration) to a specific user in the user pool.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-idp-2016-04-18/ResendConfirmationCode>`_


========
Synopsis
========

::

    resend-confirmation-code
  --client-id <value>
  [--secret-hash <value>]
  --username <value>
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


  The user name of the user to whom you wish to resend a confirmation code.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

CodeDeliveryDetails -> (structure)

  

  The code delivery details returned by the server in response to the request to resend the confirmation code.

  

  Destination -> (string)

    

    The destination for the code delivery details.

    

    

  DeliveryMedium -> (string)

    

    The delivery medium (email message or phone number).

    

    

  AttributeName -> (string)

    

    The name of the attribute in the code delivery details type.

    

    

  

