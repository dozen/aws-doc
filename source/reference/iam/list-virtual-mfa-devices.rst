[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam list-virtual-mfa-devices:


************************
list-virtual-mfa-devices
************************



===========
Description
===========



Lists the virtual MFA devices defined in the AWS account by assignment status. If you do not specify an assignment status, the action returns a list of all virtual MFA devices. Assignment status can be ``Assigned`` , ``Unassigned`` , or ``Any`` .

 

You can paginate the results using the ``MaxItems`` and ``Marker`` parameters.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/ListVirtualMFADevices>`_


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
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--assignment-status`` (string)


  The status (``Unassigned`` or ``Assigned`` ) of the devices to list. If you do not specify an ``AssignmentStatus`` , the action defaults to ``Any`` which lists both assigned and unassigned virtual MFA devices.

  

  Possible values:

  
  *   ``Assigned``

  
  *   ``Unassigned``

  
  *   ``Any``

  

  

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

      

      The Base32 seed defined as specified in `RFC3548 <https://tools.ietf.org/html/rfc3548.txt>`_ . The ``Base32StringSeed`` is Base64-encoded. 

      

      

    QRCodePNG -> (blob)

      

      A QR code PNG image that encodes ``otpauth://totp/$virtualMFADeviceName@$AccountName?secret=$Base32String`` where ``$virtualMFADeviceName`` is one of the create call arguments, ``AccountName`` is the user name if set (otherwise, the account ID otherwise), and ``Base32String`` is the seed in Base32 format. The ``Base32String`` value is Base64-encoded. 

      

      

    User -> (structure)

      

      The IAM user associated with this virtual MFA device.

      

      Path -> (string)

        

        The path to the user. For more information about paths, see `IAM Identifiers <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html>`_ in the *Using IAM* guide.

        

        

      UserName -> (string)

        

        The friendly name identifying the user.

        

        

      UserId -> (string)

        

        The stable and unique string identifying the user. For more information about IDs, see `IAM Identifiers <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html>`_ in the *Using IAM* guide.

        

        

      Arn -> (string)

        

        The Amazon Resource Name (ARN) that identifies the user. For more information about ARNs and how to use ARNs in policies, see `IAM Identifiers <http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html>`_ in the *Using IAM* guide. 

        

        

      CreateDate -> (timestamp)

        

        The date and time, in `ISO 8601 date-time format <http://www.iso.org/iso/iso8601>`_ , when the user was created.

        

        

      PasswordLastUsed -> (timestamp)

        

        The date and time, in `ISO 8601 date-time format <http://www.iso.org/iso/iso8601>`_ , when the user's password was last used to sign in to an AWS website. For a list of AWS websites that capture a user's last sign-in time, see the `Credential Reports <http://docs.aws.amazon.com/IAM/latest/UserGuide/credential-reports.html>`_ topic in the *Using IAM* guide. If a password is used more than once in a five-minute span, only the first use is returned in this field. This field is null (not present) when:

         

         
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

  

  

