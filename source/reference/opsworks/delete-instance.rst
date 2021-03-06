[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks delete-instance:


***************
delete-instance
***************



===========
Description
===========



Deletes a specified instance, which terminates the associated Amazon EC2 instance. You must stop an instance before you can delete it.

 

For more information, see `Deleting Instances <http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-delete.html>`_ .

 

 **Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/DeleteInstance>`_


========
Synopsis
========

::

    delete-instance
  --instance-id <value>
  [--delete-elastic-ip | --no-delete-elastic-ip]
  [--delete-volumes | --no-delete-volumes]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-id`` (string)


  The instance ID.

  

``--delete-elastic-ip`` | ``--no-delete-elastic-ip`` (boolean)


  Whether to delete the instance Elastic IP address.

  

``--delete-volumes`` | ``--no-delete-volumes`` (boolean)


  Whether to delete the instance's Amazon EBS volumes.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete an instance**

The following example deletes a specified instance, which is identified by its instance ID.
It also deletes any attached Amazon Elastic Block Store (Amazon EBS) volumes or Elastic IP addresses.
You can obtain an instance ID by going to the instance's details page on the AWS OpsWorks console or by
running the ``describe-instances`` command.

If the instance is online, you must first stop the instance by calling ``stop-instance``, and then
wait until the instance has stopped. You can use ``describe-instances`` to check the instance status. ::

  aws opsworks delete-instance --region us-east-1 --instance-id 3a21cfac-4a1f-4ce2-a921-b2cfba6f7771

To retain the instance's Amazon EBS volumes or Elastic IP addresses,
use the ``--no-delete-volumes`` or ``--no-delete-elastic-ip`` arguments, respectively.

*Output*: None.

**More Information**

For more information, see `Deleting AWS OpsWorks Instances`_ in the *AWS OpsWorks User Guide*.

.. _`Deleting AWS OpsWorks Instances`: http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-delete.html




======
Output
======

None