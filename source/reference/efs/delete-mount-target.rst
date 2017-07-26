[ :ref:`aws <cli:aws>` . :ref:`efs <cli:aws efs>` ]

.. _cli:aws efs delete-mount-target:


*******************
delete-mount-target
*******************



===========
Description
===========



Deletes the specified mount target.

 

This operation forcibly breaks any mounts of the file system via the mount target that is being deleted, which might disrupt instances or applications using those mounts. To avoid applications getting cut off abruptly, you might consider unmounting any mounts of the mount target, if feasible. The operation also deletes the associated network interface. Uncommitted writes may be lost, but breaking a mount target using this operation does not corrupt the file system itself. The file system you created remains. You can mount an EC2 instance in your VPC via another mount target.

 

This operation requires permissions for the following action on the file system:

 

 
* ``elasticfilesystem:DeleteMountTarget``   
 

 

.. note::

   

  The ``delete-mount-target`` call returns while the mount target state is still ``deleting`` . You can check the mount target deletion by calling the  describe-mount-targets operation, which returns a list of mount target descriptions for the given file system. 

   

 

The operation also requires permissions for the following Amazon EC2 action on the mount target's network interface:

 

 
* ``ec2:DeleteNetworkInterface``   
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticfilesystem-2015-02-01/DeleteMountTarget>`_


========
Synopsis
========

::

    delete-mount-target
  --mount-target-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--mount-target-id`` (string)


  ID of the mount target to delete (String).

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None