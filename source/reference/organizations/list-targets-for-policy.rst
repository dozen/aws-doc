[ :ref:`aws <cli:aws>` . :ref:`organizations <cli:aws organizations>` ]

.. _cli:aws organizations list-targets-for-policy:


***********************
list-targets-for-policy
***********************



===========
Description
===========



Lists all the roots, OUs, and accounts to which the specified policy is attached.

 

This operation can be called only from the organization's master account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/organizations-2016-11-28/ListTargetsForPolicy>`_


``list-targets-for-policy`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Targets``


========
Synopsis
========

::

    list-targets-for-policy
  --policy-id <value>
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--policy-id`` (string)


  The unique identifier (ID) of the policy for which you want to know its attachments.

   

  The `regex pattern <http://wikipedia.org/wiki/regex>`_ for a policy ID string requires "p-" followed by from 8 to 128 lower-case letters or digits.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``next-token`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``next-token`` is provided in the command's output. To resume pagination, provide the ``next-token`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``next-token`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To list the entities a policy is attached to**

The following example shows how to get the list of roots, OUs, and accounts to which the specified policy is attached.  

Command::

  aws organizations list-targets-for-policy --policy-id p-FullAWSAccess

Output::

  {
    "Targets": [
      {
        "Arn": "arn:aws:organizations::111111111111:root/o-exampleorgid/r-examplerootid111",
        "Name": "Root",
        "TargetId":"r-examplerootid111",
        "Type":"ROOT"
      },
      {
        "Arn": "arn:aws:organizations::111111111111:account/o-exampleorgid/333333333333;",
        "Name": "Developer Test Account",
        "TargetId": "333333333333",
        "Type": "ACCOUNT"
      },
      {
        "Arn":"arn:aws:organizations::111111111111:ou/o-exampleorgid/ou-examplerootid111-exampleouid111",
        "Name":"Accounting",
        "TargetId":"ou-examplerootid111-exampleouid111",
        "Type":"ORGANIZATIONAL_UNIT"
      }
    ]
  }

======
Output
======

Targets -> (list)

  

  A list of structures, each of which contains details about one of the entities to which the specified policy is attached.

  

  (structure)

    

    Contains information about a root, OU, or account that a policy is attached to.

    

    TargetId -> (string)

      

      The unique identifier (ID) of the policy target.

       

      The `regex pattern <http://wikipedia.org/wiki/regex>`_ for a target ID string requires one of the following:

       

       
      * Root: a string that begins with "r-" followed by from 4 to 32 lower-case letters or digits. 
       
      * Account: a string that consists of exactly 12 digits. 
       
      * Organizational unit (OU): a string that begins with "ou-" followed by from 4 to 32 lower-case letters or digits (the ID of the root that the OU is in) followed by a second "-" dash and from 8 to 32 additional lower-case letters or digits. 
       

      

      

    Arn -> (string)

      

      The Amazon Resource Name (ARN) of the policy target.

       

      For more information about ARNs in Organizations, see `ARN Formats Supported by Organizations <http://docs.aws.amazon.com/organizations/latest/userguide/orgs_permissions.html#orgs-permissions-arns>`_ in the *AWS Organizations User Guide* .

      

      

    Name -> (string)

      

      The friendly name of the policy target.

       

      The `regex pattern <http://wikipedia.org/wiki/regex>`_ that is used to validate this parameter is a string of any of the characters in the ASCII character range.

      

      

    Type -> (string)

      

      The type of the policy target.

      

      

    

  

NextToken -> (string)

  

  If present, this value indicates that there is more output available than is included in the current response. Use this value in the ``next-token`` request parameter in a subsequent call to the operation to get the next part of the output. You should repeat this until the ``next-token`` response element comes back as ``null`` .

  

  

