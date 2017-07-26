[ :ref:`aws <cli:aws>` . :ref:`efs <cli:aws efs>` ]

.. _cli:aws efs modify-mount-target-security-groups:


***********************************
modify-mount-target-security-groups
***********************************



===========
Description
===========



Modifies the set of security groups in effect for a mount target.

 

When you create a mount target, Amazon EFS also creates a new network interface (see  create-mount-target ). This operation replaces the security groups in effect for the network interface associated with a mount target, with the ``security-groups`` provided in the request. This operation requires that the network interface of the mount target has been created and the life cycle state of the mount target is not "deleted". 

 

The operation requires permissions for the following actions:

 

 
* ``elasticfilesystem:ModifyMountTargetSecurityGroups`` action on the mount target's file system. 
 
* ``ec2:ModifyNetworkInterfaceAttribute`` action on the mount target's network interface. 
 



.. note::

  **AWS CLI support for this service is only available in a preview stage.** You can enable this service by running: ``aws configure set preview.efs true`` 



========
Synopsis
========

::

    modify-mount-target-security-groups
  --mount-target-id <value>
  [--security-groups <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--mount-target-id`` (string)


  The ID of the mount target whose security groups you want to modify.

  

``--security-groups`` (list)


  An array of up to five VPC security group IDs.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None