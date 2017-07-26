[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam update-group:


************
update-group
************



===========
Description
===========



Updates the name and/or the path of the specified group.

 

.. warning::

  You should understand the implications of changing a group's path or name. For more information, see `Renaming Users and Groups`_ in the *IAM User Guide* . 

 

.. note::

  To change a group name the requester must have appropriate permissions on both the source object and the target object. For example, to change Managers to MGRs, the entity making the request must have permission on Managers and MGRs, or must have permission on all (*). For more information about permissions, see `Permissions and Policies`_ . 



========
Synopsis
========

::

    update-group
  --group-name <value>
  [--new-path <value>]
  [--new-group-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--group-name`` (string)


  Name of the group to update. If you're changing the name of the group, this is the original name. 

  

``--new-path`` (string)


  New path for the group. Only include this if changing the group's path.

  

``--new-group-name`` (string)


  New name for the group. Only include this if changing the group's name.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To rename an IAM group**

The following ``update-group`` command changes the name of the IAM group ``Test`` to ``Test-1``::

  aws iam update-group --group-name Test --new-group-name Test-1

For more information, see `Changing a Group's Name or Path`_ in the *Using IAM* guide.

.. _`Changing a Group's Name or Path`: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_RenamingGroup.html



======
Output
======

None

.. _Renaming Users and Groups: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_WorkingWithGroupsAndUsers.html
.. _Permissions and Policies: http://docs.aws.amazon.com/IAM/latest/UserGuide/PermissionsAndPolicies.html
