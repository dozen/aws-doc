[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam list-mfa-devices:


****************
list-mfa-devices
****************



===========
Description
===========



Lists the MFA devices. If the request includes the user name, then this action lists all the MFA devices associated with the specified user name. If you do not specify a user name, IAM determines the user name implicitly based on the AWS access key ID signing the request. 

 

You can paginate the results using the ``MaxItems`` and ``Marker`` parameters. 



``list-mfa-devices`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``MFADevices``


========
Synopsis
========

::

    list-mfa-devices
  [--user-name <value>]
  [--max-items <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--user-name`` (string)


  The name of the user whose MFA devices you want to list.

  

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

**To list all MFA devices for a specified user**

This example returns details about the MFA device assigned to the IAM user ``Bob``::

  aws iam list-mfa-devices --user-name Bob 

Output::

  {
    "MFADevices": [
      {
        "UserName": "Bob",
        "SerialNumber": "arn:aws:iam::123456789012:mfa/BobsMFADevice",
        "EnablDate": "2015-06-16T22:36:37Z"
      }
    ]
  }

For more information, see `Using Multi-Factor Authentication (MFA) Devices with AWS`_ in the *Using IAM* guide.

.. _`Using Multi-Factor Authentication (MFA) Devices with AWS`: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_ManagingMFA.html

======
Output
======

MFADevices -> (list)

  

  A list of MFA devices.

  

  (structure)

    

    Contains information about an MFA device.

     

    This data type is used as a response element in the  list-mfa-devices action.

    

    UserName -> (string)

      

      The user with whom the MFA device is associated.

      

      

    SerialNumber -> (string)

      

      The serial number that uniquely identifies the MFA device. For virtual MFA devices, the serial number is the device ARN. 

      

      

    EnableDate -> (timestamp)

      

      The date when the MFA device was enabled for the user.

      

      

    

  

IsTruncated -> (boolean)

  

  A flag that indicates whether there are more items to return. If your results were truncated, you can make a subsequent pagination request using the ``Marker`` request parameter to retrieve more items. Note that IAM might return fewer than the ``MaxItems`` number of results even when there are more results available. We recommend that you check ``IsTruncated`` after every call to ensure that you receive all of your results.

  

  

Marker -> (string)

  

  When ``IsTruncated`` is ``true`` , this element is present and contains the value to use for the ``Marker`` parameter in a subsequent pagination request.

  

  

