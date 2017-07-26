[ :ref:`aws <cli:aws>` . :ref:`cognito-idp <cli:aws cognito-idp>` ]

.. _cli:aws cognito-idp get-user-attribute-verification-code:


************************************
get-user-attribute-verification-code
************************************



===========
Description
===========



Gets the user attribute verification code for the specified attribute name.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-idp-2016-04-18/GetUserAttributeVerificationCode>`_


========
Synopsis
========

::

    get-user-attribute-verification-code
  --access-token <value>
  --attribute-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--access-token`` (string)


  The access token returned by the server response to get the user attribute verification code.

  

``--attribute-name`` (string)


  The attribute name returned by the server response to get the user attribute verification code.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

CodeDeliveryDetails -> (structure)

  

  The code delivery details returned by the server in response to the request to get the user attribute verification code.

  

  Destination -> (string)

    

    The destination for the code delivery details.

    

    

  DeliveryMedium -> (string)

    

    The delivery medium (email message or phone number).

    

    

  AttributeName -> (string)

    

    The name of the attribute in the code delivery details type.

    

    

  

