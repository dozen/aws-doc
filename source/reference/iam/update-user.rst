[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam update-user:


***********
update-user
***********



===========
Description
===========



Updates the name and/or the path of the specified IAM user.

 

.. warning::

   

  You should understand the implications of changing an IAM user's path or name. For more information, see `Renaming an IAM User <http://docs.aws.amazon.com/IAM/latest/UserGuide/id_users_manage.html#id_users_renaming>`_ and `Renaming an IAM Group <http://docs.aws.amazon.com/IAM/latest/UserGuide/id_groups_manage_rename.html>`_ in the *IAM User Guide* .

   

 

.. note::

   

  To change a user name the requester must have appropriate permissions on both the source object and the target object. For example, to change Bob to Robert, the entity making the request must have permission on Bob and Robert, or must have permission on all (*). For more information about permissions, see `Permissions and Policies <http://docs.aws.amazon.com/IAM/latest/UserGuide/PermissionsAndPolicies.html>`_ . 

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/UpdateUser>`_


========
Synopsis
========

::

    update-user
  --user-name <value>
  [--new-path <value>]
  [--new-user-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--user-name`` (string)


  Name of the user to update. If you're changing the name of the user, this is the original user name.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

  

``--new-path`` (string)


  New path for the IAM user. Include this parameter only if you're changing the user's path.

   

  This paramater allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of either a forward slash (/) by itself or a string that must begin and end with forward slashes, containing any ASCII character from the ! (\u0021) thru the DEL character (\u007F), including most punctuation characters, digits, and upper and lowercased letters.

  

``--new-user-name`` (string)


  New name for the user. Include this parameter only if you're changing the user's name.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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