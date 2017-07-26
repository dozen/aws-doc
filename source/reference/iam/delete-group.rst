[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam delete-group:


************
delete-group
************



===========
Description
===========



Deletes the specified group. The group must not contain any users or have any attached policies. 



========
Synopsis
========

::

    delete-group
  --group-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--group-name`` (string)


  The name of the group to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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