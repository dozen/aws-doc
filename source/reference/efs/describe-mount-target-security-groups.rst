[ :ref:`aws <cli:aws>` . :ref:`efs <cli:aws efs>` ]

.. _cli:aws efs describe-mount-target-security-groups:


*************************************
describe-mount-target-security-groups
*************************************



===========
Description
===========



Returns the security groups currently in effect for a mount target. This operation requires that the network interface of the mount target has been created and the lifecycle state of the mount target is not ``deleted`` .

 

This operation requires permissions for the following actions:

 

 
* ``elasticfilesystem:DescribeMountTargetSecurityGroups`` action on the mount target's file system.  
 
* ``ec2:DescribeNetworkInterfaceAttribute`` action on the mount target's network interface.  
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticfilesystem-2015-02-01/DescribeMountTargetSecurityGroups>`_


========
Synopsis
========

::

    describe-mount-target-security-groups
  --mount-target-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--mount-target-id`` (string)


  ID of the mount target whose security groups you want to retrieve.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

SecurityGroups -> (list)

  

  Array of security groups.

  

  (string)

    

    

  

