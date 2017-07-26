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

   

 

For more information, see `Deleting an Amazon EBS Volume <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-deleting-volume.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DeleteVolume>`_


========
Synopsis
========

::

    delete-volume
  --volume-id <value>
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--volume-id`` (string)


  The ID of the volume.

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete a volume**

This example command deletes an available volume with the volume ID of ``vol-049df61146c4d7901``. If the command succeeds, no output is returned.

Command::

  aws ec2 delete-volume --volume-id vol-049df61146c4d7901


======
Output
======

None