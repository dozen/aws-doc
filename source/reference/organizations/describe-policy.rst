[ :ref:`aws <cli:aws>` . :ref:`organizations <cli:aws organizations>` ]

.. _cli:aws organizations describe-policy:


***************
describe-policy
***************



===========
Description
===========



Retrieves information about a policy.

 

This operation can be called only from the organization's master account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/organizations-2016-11-28/DescribePolicy>`_


========
Synopsis
========

::

    describe-policy
  --policy-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--policy-id`` (string)


  The unique identifier (ID) of the policy that you want details about. You can get the ID from the  list-policies or  list-policies-for-target operations.

   

  The `regex pattern <http://wikipedia.org/wiki/regex>`_ for a policy ID string requires "p-" followed by from 8 to 128 lower-case letters or digits.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get details about a policy**

The following example shows how to request information about a policy.

Command::

  aws organizations describe-policy --policy-id p-examplepolicyid111
  
Output::

  {
    "Policy": {
      "Content": "{\n  \"Version\": \"2012-10-17\",\n  \"Statement\": [\n    {\n      \"Effect\": \"Allow\",\n      \"Action\": \"*\",\n      \"Resource\": \"*\"\n    }\n  ]\n}",
      "PolicySummary": {
        "Arn": "arn:aws:organizations::111111111111:policy/o-exampleorgid/service_control_policy/p-examplepolicyid111",
        "Type": "SERVICE_CONTROL_POLICY",
        "Id": "p-examplepolicyid111",
        "AwsManaged": false,
        "Name": "AllowAllS3Actions",
        "Description": "Enables admins to delegate S3 permissions"
      }
    }
  }

======
Output
======

Policy -> (structure)

  

  A structure that contains details about the specified policy.

  

  PolicySummary -> (structure)

    

    A structure that contains additional details about the policy.

    

    Id -> (string)

      

      The unique identifier (ID) of the policy.

       

      The `regex pattern <http://wikipedia.org/wiki/regex>`_ for a policy ID string requires "p-" followed by from 8 to 128 lower-case letters or digits.

      

      

    Arn -> (string)

      

      The Amazon Resource Name (ARN) of the policy.

       

      For more information about ARNs in Organizations, see `ARN Formats Supported by Organizations <http://docs.aws.amazon.com/organizations/latest/userguide/orgs_permissions.html#orgs-permissions-arns>`_ in the *AWS Organizations User Guide* .

      

      

    Name -> (string)

      

      The friendly name of the policy.

       

      The `regex pattern <http://wikipedia.org/wiki/regex>`_ that is used to validate this parameter is a string of any of the characters in the ASCII character range.

      

      

    Description -> (string)

      

      The description of the policy.

      

      

    Type -> (string)

      

      The type of policy.

      

      

    AwsManaged -> (boolean)

      

      A boolean value that indicates whether the specified policy is an AWS managed policy. If true, then you can attach the policy to roots, OUs, or accounts, but you cannot edit it.

      

      

    

  Content -> (string)

    

    The text content of the policy.

    

    

  

