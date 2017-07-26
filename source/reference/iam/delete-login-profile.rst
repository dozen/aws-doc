[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam delete-login-profile:


********************
delete-login-profile
********************



===========
Description
===========



Deletes the password for the specified user, which terminates the user's ability to access AWS services through the AWS Management Console. 

 

.. warning::

  Deleting a user's password does not prevent a user from accessing IAM through the command line interface or the API. To prevent all user access you must also either make the access key inactive or delete it. For more information about making keys inactive or deleting them, see  update-access-key and  delete-access-key . 



========
Synopsis
========

::

    delete-login-profile
  --user-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--user-name`` (string)


  The name of the user whose password you want to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete a password for an IAM user**

The following ``delete-login-profile`` command deletes the password for the IAM user named ``Bob``::

  aws iam delete-login-profile --user-name Bob

For more information, see `Managing Passwords`_ in the *Using IAM* guide.

.. _`Managing Passwords`: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_ManagingLogins.html




======
Output
======

None