[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 delete-volume:


*************
delete-volume
*************



===========
Description
===========



Deletes the specified EBS volume. The volume must be in the ``available`` state (not attached to an instance).

 

.. note::

   

  The volume may remain in the ``deleting`` state for several minutes.

   

 

For more information, see `Deleting an Amazon EBS Volume`_ in the *Amazon Elastic Compute Cloud User Guide* .



========
Synopsis
========

::

    delete-volume
  [--dry-run | --no-dry-run]
  --volume-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--volume-id`` (string)


  The ID of the volume.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To delete a volume**

This example command deletes an available volume with the volume ID of ``vol-1234abcd``. If the command succeeds, no output is returned.

Command::

  aws ec2 delete-volume --volume-id vol-1234abcd


======
Output
======

None

.. _Deleting an Amazon EBS Volume: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-deleting-volume.html
