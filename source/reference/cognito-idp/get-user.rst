[ :ref:`aws <cli:aws>` . :ref:`cognito-idp <cli:aws cognito-idp>` ]

.. _cli:aws cognito-idp get-user:


********
get-user
********



===========
Description
===========



Gets the user attributes and metadata for a user.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-idp-2016-04-18/GetUser>`_


========
Synopsis
========

::

    get-user
  --access-token <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--access-token`` (string)


  The access token returned by the server response to get information about the user.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Username -> (string)

  

  The user name of the user you wish to retrieve from the get user request.

  

  

UserAttributes -> (list)

  

  An array of name-value pairs representing user attributes.

   

  For custom attributes, you must prepend the ``custom:`` prefix to the attribute name.

  

  (structure)

    

    Specifies whether the attribute is standard or custom.

    

    Name -> (string)

      

      The name of the attribute.

      

      

    Value -> (string)

      

      The value of the attribute.

      

      

    

  

MFAOptions -> (list)

  

  Specifies the options for MFA (e.g., email or phone number).

  

  (structure)

    

    Specifies the different settings for multi-factor authentication (MFA).

    

    DeliveryMedium -> (string)

      

      The delivery medium (email message or SMS message) to send the MFA code.

      

      

    AttributeName -> (string)

      

      The attribute name of the MFA option type.

      

      

    

  

