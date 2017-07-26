[ :ref:`aws <cli:aws>` . :ref:`cognito-idp <cli:aws cognito-idp>` ]

.. _cli:aws cognito-idp update-user-attributes:


**********************
update-user-attributes
**********************



===========
Description
===========



Allows a user to update a specific attribute (one at a time).



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-idp-2016-04-18/UpdateUserAttributes>`_


========
Synopsis
========

::

    update-user-attributes
  --user-attributes <value>
  --access-token <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

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



``--access-token`` (string)


  The access token for the request to update user attributes.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

CodeDeliveryDetailsList -> (list)

  

  The code delivery details list from the server for the request to update user attributes.

  

  (structure)

    

    The type of code delivery details being returned from the server.

    

    Destination -> (string)

      

      The destination for the code delivery details.

      

      

    DeliveryMedium -> (string)

      

      The delivery medium (email message or phone number).

      

      

    AttributeName -> (string)

      

      The name of the attribute in the code delivery details type.

      

      

    

  

