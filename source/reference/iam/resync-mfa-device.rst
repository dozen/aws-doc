[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam resync-mfa-device:


*****************
resync-mfa-device
*****************



===========
Description
===========



Synchronizes the specified MFA device with its IAM resource object on the AWS servers.

 

For more information about creating and working with virtual MFA devices, go to `Using a Virtual MFA Device <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_VirtualMFA.html>`_ in the *IAM User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/ResyncMFADevice>`_


========
Synopsis
========

::

    resync-mfa-device
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


  The name of the user whose MFA device you want to resynchronize.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

  

``--serial-number`` (string)


  Serial number that uniquely identifies the MFA device.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

  

``--authentication-code-1`` (string)


  An authentication code emitted by the device.

   

  The format for this parameter is a sequence of six digits.

  

``--authentication-code-2`` (string)


  A subsequent authentication code emitted by the device.

   

  The format for this parameter is a sequence of six digits.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To synchronize the specified MFA device with AWS servers**

This example synchronizes the MFA device that is associated with the IAM user ``Bob`` and whose ARN is ``arn:aws:iam::123456789012:mfa/BobsMFADevice`` 
with an authenticator program that provided the two authentication codes::

  aws iam resync-mfa-device --user-name Bob --serial-number arn:aws:iam::210987654321:mfa/BobsMFADevice --authentication-code-1 123456 --authentication-code-2 987654


For more information, see `Using Multi-Factor Authentication (MFA) Devices with AWS`_ in the *IAM User* guide.

.. _`Using Multi-Factor Authentication (MFA) Devices with AWS`: http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_mfa.html

======
Output
======

None