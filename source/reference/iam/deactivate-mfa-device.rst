[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam deactivate-mfa-device:


*********************
deactivate-mfa-device
*********************



===========
Description
===========



Deactivates the specified MFA device and removes it from association with the user name for which it was originally enabled. 

 

For more information about creating and working with virtual MFA devices, go to `Using a Virtual MFA Device`_ in the *Using IAM* guide. 



========
Synopsis
========

::

    deactivate-mfa-device
  --user-name <value>
  --serial-number <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--user-name`` (string)


  The name of the user whose MFA device you want to deactivate.

  

``--serial-number`` (string)


  The serial number that uniquely identifies the MFA device. For virtual MFA devices, the serial number is the device ARN. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To deactivate an MFA device**

This command deactivates the virtual MFA device with the ARN ``arn:aws:iam::210987654321:mfa/BobsMFADevice`` that is associated with the user ``Bob``::

  aws iam deactivate-mfa-device --user-name Bob --serial-number arn:aws:iam::210987654321:mfa/BobsMFADevice


For more information, see `Using Multi-Factor Authentication (MFA) Devices with AWS`_ in the *Using IAM* guide.

.. _`Using Multi-Factor Authentication (MFA) Devices with AWS`: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_ManagingMFA.html

======
Output
======

None

.. _Using a Virtual MFA Device: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_VirtualMFA.html
