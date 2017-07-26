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
 
* You cannot use this action with instances that were created with AWS OpsWorks Stacks. 
 

 

 **Required Permissions** : To use this action, an AWS Identity and Access Management (IAM) user must have a Manage permissions level for the stack or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/AssignInstance>`_


========
Synopsis
========

::

    assign-instance
  --instance-id <value>
  --layer-ids <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To assign a registered instance to a layer**

The following example assigns a registered instance to a custom layer. ::

  aws opsworks --region us-east-1 assign-instance --instance-id 4d6d1710-ded9-42a1-b08e-b043ad7af1e2 --layer-ids 26cf1d32-6876-42fa-bbf1-9cadc0bff938

*Output*: None.

**More Information**

For more information, see `Assigning a Registered Instance to a Layer`_ in the *AWS OpsWorks User Guide*.

.. _`Assigning a Registered Instance to a Layer`: http://docs.aws.amazon.com/opsworks/latest/userguide/registered-instances-assign.html



======
Output
======

None