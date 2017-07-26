[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam get-login-profile:


*****************
get-login-profile
*****************



===========
Description
===========



Retrieves the user name and password-creation date for the specified IAM user. If the user has not been assigned a password, the action returns a 404 (``NoSuchEntity`` ) error.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/GetLoginProfile>`_


========
Synopsis
========

::

    get-login-profile
  --user-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--user-name`` (string)


  The name of the user whose login profile you want to retrieve.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get password information for an IAM user**

The following ``get-login-profile`` command gets information about the password for the IAM user named ``Bob``::

  aws iam get-login-profile --user-name Bob

Output::

  {
      "LoginProfile": {
          "UserName": "Bob",
          "CreateDate": "2012-09-21T23:03:39Z"
      }
  }

The ``get-login-profile`` command can be used to verify that an IAM user has a password. The command returns a ``NoSuchEntity``
error if no password is defined for the user.

You cannot recover a password using this command. If the password is lost, you must delete the login profile (``delete-login-profile``) for the user and then create a new one (``create-login-profile``).

For more information, see `Managing Passwords`_ in the *Using IAM* guide.

.. _`Managing Passwords`: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_ManagingLogins.html




======
Output
======

LoginProfile -> (structure)

  

  A structure containing the user name and password create date for the user.

  

  UserName -> (string)

    

    The name of the user, which can be used for signing in to the AWS Management Console.

    

    

  CreateDate -> (timestamp)

    

    The date when the password for the user was created.

    

    

  PasswordResetRequired -> (boolean)

    

    Specifies whether the user is required to set a new password on next sign-in.

    

    

  

