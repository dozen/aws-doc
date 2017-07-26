[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks assign-instance:


***************
assign-instance
***************



===========
Description
===========



Assign a registered instance to a layer.

 

 
* You can assign registered on-premises instances to any layer type.
 
* You can assign registered Amazon EC2 instances only to custom layers.
 
* You cannot use this action with instances that were created with AWS OpsWorks.
 

 

**Required Permissions** : To use this action, an AWS Identity and Access Management (IAM) user must have a Manage permissions level for the stack or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    assign-instance
  --instance-id <value>
  --layer-ids <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--instance-id`` (string)


  The instance ID.

  

``--layer-ids`` (list)


  The layer ID, which must correspond to a custom layer. You cannot assign a registered instance to a built-in layer.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To assign a registered instance to a layer**

The following example assigns a registered instance to a custom layer. ::

  aws opsworks --region us-east-1 assign-instance --instance-id 4d6d1710-ded9-42a1-b08e-b043ad7af1e2 --layer-ids 26cf1d32-6876-42fa-bbf1-9cadc0bff938

**Note**: OpsWorks CLI commands should set the region to ``us-east-1`` regardless of the stack's location.

*Output*: None.

**More Information**

For more information, see `Assigning a Registered Instance to a Layer`_ in the *AWS OpsWorks User Guide*.

.. _`Assigning a Registered Instance to a Layer`: http://docs.aws.amazon.com/opsworks/latest/userguide/registered-instances-assign.html



======
Output
======

None

.. _Managing User Permissions: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html
