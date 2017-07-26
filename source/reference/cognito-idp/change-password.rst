[ :ref:`aws <cli:aws>` . :ref:`cognito-idp <cli:aws cognito-idp>` ]

.. _cli:aws cognito-idp change-password:


***************
change-password
***************



===========
Description
===========



Changes the password for a specified user in a user pool.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-idp-2016-04-18/ChangePassword>`_


========
Synopsis
========

::

    change-password
  --previous-password <value>
  --proposed-password <value>
  --access-token <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--previous-password`` (string)


  The old password in the change password request.

  

``--proposed-password`` (string)


  The new password in the change password request.

  

``--access-token`` (string)


  The access token in the change password request.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

