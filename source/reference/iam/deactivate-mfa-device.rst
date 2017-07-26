[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam deactivate-mfa-device:


*********************
deactivate-mfa-device
*********************



===========
Description
===========



Deactivates the specified MFA device and removes it from association with the user name for which it was originally enabled.

 

For more information about creating and working with virtual MFA devices, go to `Using a Virtual MFA Device <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_VirtualMFA.html>`_ in the *IAM User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/DeactivateMFADevice>`_


========
Synopsis
========

::

    deactivate-mfa-device
  --user-name <value>
  --serial-number <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--user-name`` (string)


  The name of the user whose MFA device you want to deactivate.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@-

  

``--serial-number`` (string)


  The serial number that uniquely identifies the MFA device. For virtual MFA devices, the serial number is the device ARN.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@:/-

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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