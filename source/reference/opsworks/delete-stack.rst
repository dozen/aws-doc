[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks delete-stack:


************
delete-stack
************



===========
Description
===========



Deletes a specified stack. You must first delete all instances, layers, and apps or deregister registered instances. For more information, see `Shut Down a Stack <http://docs.aws.amazon.com/opsworks/latest/userguide/workingstacks-shutting.html>`_ .

 

 **Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/DeleteStack>`_


========
Synopsis
========

::

    delete-stack
  --stack-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stack-id`` (string)


  The stack ID.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

*Output*: None.

**More Information**

For more information, see `Shut Down a Stack`_ in the *AWS OpsWorks User Guide*.

.. _`Shut Down a Stack`: http://docs.aws.amazon.com/opsworks/latest/userguide/workingstacks-shutting.html


======
Output
======

None