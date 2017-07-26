[ :ref:`aws <cli:aws>` . :ref:`cognito-idp <cli:aws cognito-idp>` ]

.. _cli:aws cognito-idp sign-up:


*******
sign-up
*******



===========
Description
===========



Registers the user in the specified user pool and creates a user name, password, and user attributes.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-idp-2016-04-18/SignUp>`_


========
Synopsis
========

::

    sign-up
  --client-id <value>
  [--secret-hash <value>]
  --username <value>
  --password <value>
  [--user-attributes <value>]
  [--validation-data <value>]
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


  The user name of the user you wish to register.

  

``--password`` (string)


  The password of the user you wish to register.

  

``--user-attributes`` (list)


  An array of name-value pairs representing user attributes.

   

  For custom attributes, you must prepend the ``custom:`` prefix to the attribute name.

  



Shorthand Syntax::

    Name=string,Value=string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Value": "string"
    }
    ...
  ]



``--validation-data`` (list)


  The validation data in the request to register a user.

  



Shorthand Syntax::

    Name=string,Value=string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Value": "string"
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

UserConfirmed -> (boolean)

  

  A response from the server indicating that a user registration has been confirmed.

  

  

CodeDeliveryDetails -> (structure)

  

  The code delivery details returned by the server response to the user registration request.

  

  Destination -> (string)

    

    The destination for the code delivery details.

    

    

  DeliveryMedium -> (string)

    

    The delivery medium (email message or phone number).

    

    

  AttributeName -> (string)

    

    The name of the attribute in the code delivery details type.

    

    

  

UserSub -> (string)

  

  The UUID of the authenticated user. This is not the same as ``username`` .

  

  

