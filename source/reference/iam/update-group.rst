[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam update-group:


************
update-group
************



===========
Description
===========



Updates the name and/or the path of the specified IAM group.

 

.. warning::

   

  You should understand the implications of changing a group's path or name. For more information, see `Renaming Users and Groups <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_WorkingWithGroupsAndUsers.html>`_ in the *IAM User Guide* .

   

 

.. note::

   

  To change an IAM group name the requester must have appropriate permissions on both the source object and the target object. For example, to change "Managers" to "MGRs", the entity making the request must have permission on both "Managers" and "MGRs", or must have permission on all (*). For more information about permissions, see `Permissions and Policies <http://docs.aws.amazon.com/IAM/latest/UserGuide/PermissionsAndPolicies.html>`_ . 

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/UpdateGroup>`_


========
Synopsis
========

::

    update-group
  --group-name <value>
  [--new-path <value>]
  [--new-group-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--group-name`` (string)


  Name of the IAM group to update. If you're changing the name of the group, this is the original name.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

  

``--new-path`` (string)


  New path for the IAM group. Only include this if changing the group's path.

   

  This paramater allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

  

``--new-group-name`` (string)


  New name for the IAM group. Only include this if changing the group's name.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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