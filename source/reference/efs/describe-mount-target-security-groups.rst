[ :ref:`aws <cli:aws>` . :ref:`efs <cli:aws efs>` ]

.. _cli:aws efs describe-mount-target-security-groups:


*************************************
describe-mount-target-security-groups
*************************************



===========
Description
===========



Returns the security groups currently in effect for a mount target. This operation requires that the network interface of the mount target has been created and the life cycle state of the mount target is not "deleted".

 

This operation requires permissions for the following actions:

 

 
* ``elasticfilesystem:DescribeMountTargetSecurityGroups`` action on the mount target's file system. 
 
* ``ec2:DescribeNetworkInterfaceAttribute`` action on the mount target's network interface. 
 



.. note::

  **AWS CLI support for this service is only available in a preview stage.** You can enable this service by running: ``aws configure set preview.efs true`` 



========
Synopsis
========

::

    describe-mount-target-security-groups
  --mount-target-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--mount-target-id`` (string)


  The ID of the mount target whose security groups you want to retrieve.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

SecurityGroups -> (list)

  

  An array of security groups.

  

  (string)

    

    

  

