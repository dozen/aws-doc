[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam update-user:


***********
update-user
***********



===========
Description
===========



Updates the name and/or the path of the specified user.

 

.. warning::

  You should understand the implications of changing a user's path or name. For more information, see `Renaming Users and Groups`_ in the *IAM User Guide* . 

 

.. note::

  To change a user name the requester must have appropriate permissions on both the source object and the target object. For example, to change Bob to Robert, the entity making the request must have permission on Bob and Robert, or must have permission on all (*). For more information about permissions, see `Permissions and Policies`_ . 



========
Synopsis
========

::

    update-user
  --user-name <value>
  [--new-path <value>]
  [--new-user-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--user-name`` (string)


  Name of the user to update. If you're changing the name of the user, this is the original user name. 

  

``--new-path`` (string)


  New path for the user. Include this parameter only if you're changing the user's path.

  

``--new-user-name`` (string)


  New name for the user. Include this parameter only if you're changing the user's name.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To change an IAM user's name**

The following ``update-user`` command changes the name of the IAM user ``Bob`` to ``Robert``::

  aws iam update-user --user-name Bob --new-user-name Robert

For more information, see `Changing a Group's Name or Path`_ in the *Using IAM* guide.

.. _`Changing a Group's Name or Path`: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_RenamingGroup.html



======
Output
======

None

.. _Renaming Users and Groups: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_WorkingWithGroupsAndUsers.html
.. _Permissions and Policies: http://docs.aws.amazon.com/IAM/latest/UserGuide/PermissionsAndPolicies.html
