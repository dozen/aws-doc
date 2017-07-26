[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 reset-image-attribute:


*********************
reset-image-attribute
*********************



===========
Description
===========



Resets an attribute of an AMI to its default value.

 

.. note::

  

  The productCodes attribute can't be reset. 

  



========
Synopsis
========

::

    reset-image-attribute
  [--dry-run | --no-dry-run]
  --image-id <value>
  --attribute <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--image-id`` (string)


  The ID of the AMI.

  

``--attribute`` (string)


  The attribute to reset (currently you can only reset the launch permission attribute).

  

  Possible values:

  
  *   ``launchPermission``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To reset the launchPermission attribute**

This example resets the ``launchPermission`` attribute for the specified AMI to its default value. By default, AMIs are private. If the command succeeds, no output is returned.

Command::

  aws ec2 reset-image-attribute --image-id ami-5731123e --attribute launchPermission


======
Output
======

None