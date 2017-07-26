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

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/ResetImageAttribute>`_


========
Synopsis
========

::

    reset-image-attribute
  --attribute <value>
  --image-id <value>
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--attribute`` (string)


  The attribute to reset (currently you can only reset the launch permission attribute).

  

  Possible values:

  
  *   ``launchPermission``

  

  

``--image-id`` (string)


  The ID of the AMI.

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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