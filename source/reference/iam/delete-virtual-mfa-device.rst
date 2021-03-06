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

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/DeleteVirtualMFADevice>`_


========
Synopsis
========

::

    delete-virtual-mfa-device
  --serial-number <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--serial-number`` (string)


  The serial number that uniquely identifies the MFA device. For virtual MFA devices, the serial number is the same as the ARN.

   

  This parameter allows (per its `regex pattern <http://wikipedia.org/wiki/regex>`_ ) a string of characters consisting of upper and lowercase alphanumeric characters with no spaces. You can also include any of the following characters: =,.@:/-

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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