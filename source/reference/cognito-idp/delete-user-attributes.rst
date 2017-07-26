[ :ref:`aws <cli:aws>` . :ref:`cognito-idp <cli:aws cognito-idp>` ]

.. _cli:aws cognito-idp delete-user-attributes:


**********************
delete-user-attributes
**********************



===========
Description
===========



Deletes the attributes for a user.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-idp-2016-04-18/DeleteUserAttributes>`_


========
Synopsis
========

::

    delete-user-attributes
  --user-attribute-names <value>
  --access-token <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--user-attribute-names`` (list)


  An array of strings representing the user attribute names you wish to delete.

   

  For custom attributes, you must prepend the ``custom:`` prefix to the attribute name.

  



Syntax::

  "string" "string" ...



``--access-token`` (string)


  The access token used in the request to delete user attributes.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

