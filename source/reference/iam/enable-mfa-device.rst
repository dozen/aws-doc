[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam enable-mfa-device:


*****************
enable-mfa-device
*****************



===========
Description
===========



Enables the specified MFA device and associates it with the specified IAM user. When enabled, the MFA device is required for every subsequent login by the IAM user associated with the device.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/EnableMFADevice>`_


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
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--user-name`` (string)


  The name of the IAM user for whom you want to enable the MFA device.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

  

``--serial-number`` (string)


  The serial number that uniquely identifies the MFA device. For virtual MFA devices, the serial number is the device ARN.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@:/-

  

``--authentication-code-1`` (string)


  An authentication code emitted by the device. 

   

  The format for this parameter is a string of 6 digits.

   

  .. warning::

     

    Submit your request immediately after generating the authentication codes. If you generate the codes and then wait too long to submit the request, the MFA device successfully associates with the user but the MFA device becomes out of sync. This happens because time-based one-time passwords (TOTP) expire after a short period of time. If this happens, you can `resync the device <http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_mfa_sync.html>`_ .

     

  

``--authentication-code-2`` (string)


  A subsequent authentication code emitted by the device.

   

  The format for this parameter is a string of 6 digits.

   

  .. warning::

     

    Submit your request immediately after generating the authentication codes. If you generate the codes and then wait too long to submit the request, the MFA device successfully associates with the user but the MFA device becomes out of sync. This happens because time-based one-time passwords (TOTP) expire after a short period of time. If this happens, you can `resync the device <http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_mfa_sync.html>`_ .

     

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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