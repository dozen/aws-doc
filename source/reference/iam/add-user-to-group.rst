[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam add-user-to-group:


*****************
add-user-to-group
*****************



===========
Description
===========



Adds the specified user to the specified group.



========
Synopsis
========

::

    add-user-to-group
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


  The name of the user to add.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To add a user to an IAM group**

The following ``add-user-to-group`` command adds an IAM user named ``Bob`` to the IAM group named ``Admins``::

  aws iam add-user-to-group --user-name Bob --group-name Admins

For more information, see `Adding and Removing Users in an IAM Group`_ in the *Using IAM* guide.

.. _`Adding and Removing Users in an IAM Group`: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_AddOrRemoveUsersFromGroup.html



======
Output
======

None