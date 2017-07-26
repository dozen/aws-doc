[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam delete-user:


***********
delete-user
***********



===========
Description
===========



Deletes the specified user. The user must not belong to any groups, have any keys or signing certificates, or have any attached policies. 



========
Synopsis
========

::

    delete-user
  --user-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--user-name`` (string)


  The name of the user to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete an IAM user**

The following ``delete-user`` command removes the IAM user named ``Bob`` from the current account::

  aws iam delete-user --user-name Bob

For more information, see `Deleting a User from Your AWS Account`_ in the *Using IAM* guide.

.. _`Deleting a User from Your AWS Account`: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_DeletingUserFromAccount.html



======
Output
======

None