[ :ref:`aws <cli:aws>` . :ref:`cognito-idp <cli:aws cognito-idp>` ]

.. _cli:aws cognito-idp admin-update-user-attributes:


****************************
admin-update-user-attributes
****************************



===========
Description
===========



Updates the specified user's attributes, including developer attributes, as an administrator. Works on any user.

 

For custom attributes, you must prepend the ``custom:`` prefix to the attribute name.

 

In addition to updating user attributes, this API can also be used to mark phone and email as verified.

 

Requires developer credentials.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-idp-2016-04-18/AdminUpdateUserAttributes>`_


========
Synopsis
========

::

    admin-update-user-attributes
  --user-pool-id <value>
  --username <value>
  --user-attributes <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--user-pool-id`` (string)


  The user pool ID for the user pool where you want to update user attributes.

  

``--username`` (string)


  The user name of the user for whom you want to update user attributes.

  

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



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

