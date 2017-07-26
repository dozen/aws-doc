[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks delete-stack:


************
delete-stack
************



===========
Description
===========



Deletes a specified stack. You must first delete all instances, layers, and apps or deregister registered instances. For more information, see `Shut Down a Stack`_ .

 

**Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    delete-stack
  --stack-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--stack-id`` (string)


  The stack ID.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete a stack**

The following example deletes a specified stack, which is identified by its stack ID.
You can obtain a stack ID by clicking **Stack Settings** on the AWS OpsWorks console or by
running the ``describe-stacks`` command.

**Note:** Before deleting a layer, you must use ``delete-app``, ``delete-instance``, and ``delete-layer``
to delete all of the stack's apps, instances, and layers. ::

  aws opsworks delete-stack --region us-east-1 --stack-id 154a9d89-7e9e-433b-8de8-617e53756c84

**Note**: AWS OpsWorks CLI commands should set the region to ``us-east-1`` regardless of the stack's location.

*Output*: None.

**More Information**

For more information, see `Shut Down a Stack`_ in the *AWS OpsWorks User Guide*.

.. _`Shut Down a Stack`: http://docs.aws.amazon.com/opsworks/latest/userguide/workingstacks-shutting.html


======
Output
======

None

.. _Managing User Permissions: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html
.. _Shut Down a Stack: http://docs.aws.amazon.com/opsworks/latest/userguide/workingstacks-shutting.html
