[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 reset-instance-attribute:


************************
reset-instance-attribute
************************



===========
Description
===========



Resets an attribute of an instance to its default value. To reset the ``kernel`` or ``ramdisk`` , the instance must be in a stopped state. To reset the ``sourceDestCheck`` , the instance can be either running or stopped.

 

The ``sourceDestCheck`` attribute controls whether source/destination checking is enabled. The default value is ``true`` , which means checking is enabled. This value must be ``false`` for a NAT instance to perform NAT. For more information, see `NAT Instances <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_NAT_Instance.html>`_ in the *Amazon Virtual Private Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/ResetInstanceAttribute>`_


========
Synopsis
========

::

    reset-instance-attribute
  --attribute <value>
  [--dry-run | --no-dry-run]
  --instance-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--attribute`` (string)


  The attribute to reset.

   

  .. warning::

     

    You can only reset the following attributes: ``kernel`` | ``ramdisk`` | ``sourceDestCheck`` . To change an instance attribute, use  modify-instance-attribute .

     

  

  Possible values:

  
  *   ``instanceType``

  
  *   ``kernel``

  
  *   ``ramdisk``

  
  *   ``userData``

  
  *   ``disableApiTermination``

  
  *   ``instanceInitiatedShutdownBehavior``

  
  *   ``rootDeviceName``

  
  *   ``blockDeviceMapping``

  
  *   ``productCodes``

  
  *   ``sourceDestCheck``

  
  *   ``groupSet``

  
  *   ``ebsOptimized``

  
  *   ``sriovNetSupport``

  
  *   ``enaSupport``

  

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--instance-id`` (string)


  The ID of the instance.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To reset the sourceDestCheck attribute**

This example resets the ``sourceDestCheck`` attribute of the specified instance. The instance must be in a VPC. If the command succeeds, no output is returned.

Command::

  aws ec2 reset-instance-attribute --instance-id i-1234567890abcdef0 --attribute sourceDestCheck

**To reset the kernel attribute**

This example resets the ``kernel`` attribute of the specified instance. The instance must be in the ``stopped`` state. If the command succeeds, no output is returned.

Command::

  aws ec2 reset-instance-attribute --instance-id i-1234567890abcdef0 --attribute kernel

**To reset the ramdisk attribute**

This example resets the ``ramdisk`` attribute of the specified instance. The instance must be in the ``stopped`` state. If the command succeeds, no output is returned.

Command::

  aws ec2 reset-instance-attribute --instance-id i-1234567890abcdef0 --attribute ramdisk


======
Output
======

None