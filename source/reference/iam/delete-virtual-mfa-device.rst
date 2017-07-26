[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam delete-virtual-mfa-device:


*************************
delete-virtual-mfa-device
*************************



===========
Description
===========



Deletes a virtual MFA device.

 

.. note::

  You must deactivate a user's virtual MFA device before you can delete it. For information about deactivating MFA devices, see  deactivate-mfa-device . 



========
Synopsis
========

::

    delete-virtual-mfa-device
  --serial-number <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--serial-number`` (string)


  The serial number that uniquely identifies the MFA device. For virtual MFA devices, the serial number is the same as the ARN. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To remove a virtual MFA device**

The following ``delete-virtual-mfa-device`` command removes the specified MFA device from the current account::

  aws iam delete-virtual-mfa-device --serial-number arn:aws:iam::123456789012:mfa/MFATest

For more information, see `Using a Virtual MFA Device with AWS`_ in the *Using IAM* guide.

.. _`Using a Virtual MFA Device with AWS`: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_VirtualMFA.html



======
Output
======

None