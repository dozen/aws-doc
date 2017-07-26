[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam delete-access-key:


*****************
delete-access-key
*****************



===========
Description
===========



Deletes the access key associated with the specified user.

 

If you do not specify a user name, IAM determines the user name implicitly based on the AWS access key ID signing the request. Because this action works for access keys under the AWS account, you can use this action to manage root credentials even if the AWS account has no associated users. 



========
Synopsis
========

::

    delete-access-key
  [--user-name <value>]
  --access-key-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--user-name`` (string)


  The name of the user whose key you want to delete.

  

``--access-key-id`` (string)


  The access key ID for the access key ID and secret access key you want to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete an access key for an IAM user**

The following ``delete-access-key`` command deletes the specified access key (access key ID and secret access key) for the IAM user named ``Bob``::

  aws iam delete-access-key --access-key AKIDPMS9RO4H3FEXAMPLE --user-name Bob

To list the access keys defined for an IAM user, use the ``list-access-keys`` command.

For more information, see `Creating, Modifying, and Viewing User Security Credentials`_ in the *Using IAM* guide.

.. _`Creating, Modifying, and Viewing User Security Credentials`: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_CreateAccessKey.html




======
Output
======

None