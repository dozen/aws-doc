[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam create-virtual-mfa-device:


*************************
create-virtual-mfa-device
*************************



===========
Description
===========



Creates a new virtual MFA device for the AWS account. After creating the virtual MFA, use  enable-mfa-device to attach the MFA device to an IAM user. For more information about creating and working with virtual MFA devices, go to `Using a Virtual MFA Device`_ in the *Using IAM* guide. 

 

For information about limits on the number of MFA devices you can create, see `Limitations on Entities`_ in the *Using IAM* guide. 

 

.. warning::

  The seed information contained in the QR code and the Base32 string should be treated like any other secret access information, such as your AWS access keys or your passwords. After you provision your virtual device, you should ensure that the information is destroyed following secure procedures. 



========
Synopsis
========

::

    create-virtual-mfa-device
  [--path <value>]
  --virtual-mfa-device-name <value>
  --outfile <value>
  --bootstrap-method <value>




=======
Options
=======

``--path`` (string)


  The path for the virtual MFA device. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide. 

   

  This parameter is optional. If it is not included, it defaults to a slash (/).

  

``--virtual-mfa-device-name`` (string)


  The name of the virtual MFA device. Use with path to uniquely identify a virtual MFA device. 

  

``--outfile`` (string)
The output path and file name where the bootstrap information will be stored.

``--bootstrap-method`` (string)
Method to use to seed the virtual MFA. Valid values are: QRCodePNG | Base32StringSeed



========
Examples
========

**To create a virtual MFA device**

This example creates a new virtual MFA device called ``BobsMFADevice``. It creates a file that contains bootstrap information called ``QRCode.png`` 
and places it in the ``C:/`` directory. The bootstrap method used in this example is ``QRCodePNG``::


  aws iam create-virtual-mfa-device --virtual-mfa-device-name BobsMFADevice --outfile C:/QRCode.png --bootstrap-method QRCodePNG

Output::

  {
      "VirtualMFADevice": {
          "SerialNumber": "arn:aws:iam::210987654321:mfa/BobsMFADevice"
  }

For more information, see `Using Multi-Factor Authentication (MFA) Devices with AWS`_ in the *Using IAM* guide.

.. _`Using Multi-Factor Authentication (MFA) Devices with AWS`: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_ManagingMFA.html

======
Output
======

VirtualMFADevice -> (structure)

  

  A newly created virtual MFA device.

  

  SerialNumber -> (string)

    

    The serial number associated with ``VirtualMFADevice`` .

    

    

  Base32StringSeed -> (blob)

    

    The Base32 seed defined as specified in `RFC3548`_ . The ``Base32StringSeed`` is Base64-encoded. 

    

    

  QRCodePNG -> (blob)

    

    A QR code PNG image that encodes ``otpauth://totp/$virtualMFADeviceName@$AccountName?secret=$Base32String`` where ``$virtualMFADeviceName`` is one of the create call arguments, ``AccountName`` is the user name if set (otherwise, the account ID otherwise), and ``Base32String`` is the seed in Base32 format. The ``Base32String`` value is Base64-encoded. 

    

    

  User -> (structure)

    

    Contains information about an IAM user entity.

     

    This data type is used as a response element in the following actions:

     

     
    *  create-user   
     
    *  get-user   
     
    *  list-users   
     

    

    Path -> (string)

      

      The path to the user. For more information about paths, see `IAM Identifiers`_ in the *Using IAM* guide.

      

      

    UserName -> (string)

      

      The friendly name identifying the user.

      

      

    UserId -> (string)

      

      The stable and unique string identifying the user. For more information about IDs, see `IAM Identifiers`_ in the *Using IAM* guide.

      

      

    Arn -> (string)

      

      The Amazon Resource Name (ARN) that identifies the user. For more information about ARNs and how to use ARNs in policies, see `IAM Identifiers`_ in the *Using IAM* guide. 

      

      

    CreateDate -> (timestamp)

      

      The date and time, in `ISO 8601 date-time format`_ , when the user was created.

      

      

    PasswordLastUsed -> (timestamp)

      

      The date and time, in `ISO 8601 date-time format`_ , when the user's password was last used to sign in to an AWS website. For a list of AWS websites that capture a user's last sign-in time, see the `Credential Reports`_ topic in the *Using IAM* guide. If a password is used more than once in a five-minute span, only the first use is returned in this field. This field is null (not present) when:

       

       
      * The user does not have a password 
       
      * The password exists but has never been used (at least not since IAM started tracking this information on October 20th, 2014 
       
      * there is no sign-in data associated with the user 
       

       

      This value is returned only in the  get-user and  list-users actions. 

      

      

    

  EnableDate -> (timestamp)

    

    The date and time on which the virtual MFA device was enabled.

    

    

  



.. _RFC3548: http://www.ietf.org/rfc/rfc3548.txt
.. _ISO 8601 date-time format: http://www.iso.org/iso/iso8601
.. _IAM Identifiers: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html
.. _Limitations on Entities: http://docs.aws.amazon.com/IAM/latest/UserGuide/LimitationsOnEntities.html
.. _Using a Virtual MFA Device: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_VirtualMFA.html
.. _Credential Reports: http://docs.aws.amazon.com/IAM/latest/UserGuide/credential-reports.html
