[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks delete-layer:


************
delete-layer
************



===========
Description
===========



Deletes a specified layer. You must first stop and then delete all associated instances or unassign registered instances. For more information, see `How to Delete a Layer <http://docs.aws.amazon.com/opsworks/latest/userguide/workinglayers-basics-delete.html>`_ .

 

 **Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/DeleteLayer>`_


========
Synopsis
========

::

    delete-layer
  --layer-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--layer-id`` (string)


  The layer ID.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete a layer**

The following example deletes a specified layer, which is identified by its layer ID.
You can obtain a layer ID by going to the layer's details page on the AWS OpsWorks console or by
running the ``describe-layers`` command.

**Note:** Before deleting a layer, you must use ``delete-instance`` to delete all of the layer's instances. ::

  aws opsworks delete-layer --region us-east-1 --layer-id a919454e-b816-4598-b29a-5796afb498ed

*Output*: None.

**More Information**

For more information, see `Deleting AWS OpsWorks Instances`_ in the *AWS OpsWorks User Guide*.

.. _`Deleting AWS OpsWorks Instances`: http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-delete.html


======
Output
======

None