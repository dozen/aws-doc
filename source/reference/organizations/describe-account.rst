[ :ref:`aws <cli:aws>` . :ref:`organizations <cli:aws organizations>` ]

.. _cli:aws organizations describe-account:


****************
describe-account
****************



===========
Description
===========



Retrieves Organizations-related information about the specified account.

 

This operation can be called only from the organization's master account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/organizations-2016-11-28/DescribeAccount>`_


========
Synopsis
========

::

    describe-account
  --account-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--account-id`` (string)


  The unique identifier (ID) of the AWS account that you want information about. You can get the ID from the  list-accounts or  list-accounts-for-parent operations.

   

  The `regex pattern <http://wikipedia.org/wiki/regex>`_ for an account ID string requires exactly 12 digits.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get information about an account**

The following example shows how to request information about member account 555555555555.

Command::

  aws organizations describe-account --account-id 555555555555
  
Output::

  {
    "Account": {
      "Id": "555555555555",
      "Arn": "arn:aws:organizations::111111111111:account/o-exampleorgid/555555555555",
      "Name": "Beta account",
      "Email": "anika@example.com",
      "JoinedMethod": "INVITED",
      "JoinedTimeStamp": 1481756563.134,
      "Status": "ACTIVE"
    }
  }

======
Output
======

Account -> (structure)

  

  A structure that contains information about the requested account.

  

  Id -> (string)

    

    The unique identifier (ID) of the account.

     

    The `regex pattern <http://wikipedia.org/wiki/regex>`_ for an account ID string requires exactly 12 digits.

    

    

  Arn -> (string)

    

    The Amazon Resource Name (ARN) of the account.

     

    For more information about ARNs in Organizations, see `ARN Formats Supported by Organizations <http://docs.aws.amazon.com/organizations/latest/userguide/orgs_permissions.html#orgs-permissions-arns>`_ in the *AWS Organizations User Guide* .

    

    

  Email -> (string)

    

    The email address associated with the AWS account.

     

    The `regex pattern <http://wikipedia.org/wiki/regex>`_ for this parameter is a string of characters that represents a standard Internet email address.

    

    

  Name -> (string)

    

    The friendly name of the account.

     

    The `regex pattern <http://wikipedia.org/wiki/regex>`_ that is used to validate this parameter is a string of any of the characters in the ASCII character range.

    

    

  Status -> (string)

    

    The status of the account in the organization.

    

    

  JoinedMethod -> (string)

    

    The method by which the account joined the organization.

    

    

  JoinedTimestamp -> (timestamp)

    

    The date the account became a part of the organization.

    

    

  

