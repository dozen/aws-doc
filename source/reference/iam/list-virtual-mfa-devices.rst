[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam list-virtual-mfa-devices:


************************
list-virtual-mfa-devices
************************



===========
Description
===========



Lists the virtual MFA devices under the AWS account by assignment status. If you do not specify an assignment status, the action returns a list of all virtual MFA devices. Assignment status can be ``Assigned`` , ``Unassigned`` , or ``Any`` . 

 

You can paginate the results using the ``MaxItems`` and ``Marker`` parameters. 



``list-virtual-mfa-devices`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``VirtualMFADevices``


========
Synopsis
========

::

    list-virtual-mfa-devices
  [--assignment-status <value>]
  [--max-items <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--assignment-status`` (string)


  The status (unassigned or assigned) of the devices to list. If you do not specify an ``AssignmentStatus`` , the action defaults to ``Any`` which lists both assigned and unassigned virtual MFA devices. 

  

  Possible values:

  
  *   ``Assigned``

  
  *   ``Unassigned``

  
  *   ``Any``

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To list virtual MFA devices**

The following ``list-virtual-mfa-devices`` command lists the virtual MFA devices that have been configured for the current account::

  aws iam list-virtual-mfa-devices

Output::

  {
    "VirtualMFADevices": [
      {
        "SerialNumber": "arn:aws:iam::123456789012:mfa/ExampleMFADevice"
      },
      {
        "SerialNumber": "arn:aws:iam::123456789012:mfa/Fred"
      }
    ]
  }

For more information, see `Using a Virtual MFA Device with AWS`_ in the *Using IAM* guide.

.. _`Using a Virtual MFA Device with AWS`: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_VirtualMFA.html



======
Output
======

VirtualMFADevices -> (list)

  

  The list of virtual MFA devices in the current account that match the ``AssignmentStatus`` value that was passed in the request. 

  

  (structure)

    

    Contains information about a virtual MFA device.

    

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

      

      

    

  

IsTruncated -> (boolean)

  

  A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

  

  

Marker -> (string)

  

  When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

  

  



.. _RFC3548: http://www.ietf.org/rfc/rfc3548.txt
.. _ISO 8601 date-time format: http://www.iso.org/iso/iso8601
.. _IAM Identifiers: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html
.. _Credential Reports: http://docs.aws.amazon.com/IAM/latest/UserGuide/credential-reports.html
