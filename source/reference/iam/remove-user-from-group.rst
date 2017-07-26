[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam remove-user-from-group:


**********************
remove-user-from-group
**********************



===========
Description
===========



Removes the specified user from the specified group.



========
Synopsis
========

::

    remove-user-from-group
  --group-name <value>
  --user-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--group-name`` (string)


  The name of the group to update.

  

``--user-name`` (string)


  The name of the user to remove.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To remove a user from an IAM group**

The following ``remove-user-from-group`` command removes the user named ``Bob`` from the IAM group named ``Admins``::

  aws iam remove-user-from-group --user-name Bob --group-name Admins

For more information, see `Adding Users to and Removing Users from a Group`_ in the *Using IAM* guide.

.. _`Adding Users to and Removing Users from a Group`: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_AddOrRemoveUsersFromGroup.html



======
Output
======

None