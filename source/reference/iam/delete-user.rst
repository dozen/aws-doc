[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam delete-user:


***********
delete-user
***********



===========
Description
===========



Deletes the specified IAM user. The user must not belong to any groups or have any access keys, signing certificates, or attached policies.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/DeleteUser>`_


========
Synopsis
========

::

    delete-user
  --user-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--user-name`` (string)


  The name of the user to delete.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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