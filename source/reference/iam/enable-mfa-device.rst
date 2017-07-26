[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam enable-mfa-device:


*****************
enable-mfa-device
*****************



===========
Description
===========



Enables the specified MFA device and associates it with the specified user name. When enabled, the MFA device is required for every subsequent login by the user name associated with the device. 



========
Synopsis
========

::

    enable-mfa-device
  --user-name <value>
  --serial-number <value>
  --authentication-code-1 <value>
  --authentication-code-2 <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--user-name`` (string)


  The name of the user for whom you want to enable the MFA device.

  

``--serial-number`` (string)


  The serial number that uniquely identifies the MFA device. For virtual MFA devices, the serial number is the device ARN. 

  

``--authentication-code-1`` (string)


  An authentication code emitted by the device.

  

``--authentication-code-2`` (string)


  A subsequent authentication code emitted by the device.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To enable an MFA device**

After you ran the ``create-virtual-mfa-device`` command to create a new virtual MFA device, you can then assign this MFA device to a user.
The following example assigns the MFA device with the serial number ``arn:aws:iam::210987654321:mfa/BobsMFADevice`` to the user ``Bob``.
The command also synchronizes the device with AWS by including the first two codes in sequence from the virtual MFA device::

  aws iam enable-mfa-device --user-name Bob --serial-number arn:aws:iam::210987654321:mfa/BobsMFADevice --authentication-code-1 123456 --authentication-code-2 789012


For more information, see `Using a Virtual MFA Device with AWS`_ in the *Using IAM* guide.

.. _`Using a Virtual MFA Device with AWS`: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_VirtualMFA.html

======
Output
======

None