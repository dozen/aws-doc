[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam delete-group:


************
delete-group
************



===========
Description
===========



Deletes the specified IAM group. The group must not contain any users or have any attached policies.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/DeleteGroup>`_


========
Synopsis
========

::

    delete-group
  --group-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--group-name`` (string)


  The name of the IAM group to delete.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete an IAM group**

The following ``delete-group`` command deletes an IAM group named ``MyTestGroup``::

  aws iam delete-group --group-name MyTestGroup


For more information, see `Deleting an IAM Group`_ in the *Using IAM* guide.

.. _`Deleting an IAM Group`: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_DeleteGroup.html

======
Output
======

None