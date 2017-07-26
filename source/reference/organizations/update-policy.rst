[ :ref:`aws <cli:aws>` . :ref:`organizations <cli:aws organizations>` ]

.. _cli:aws organizations update-policy:


*************
update-policy
*************



===========
Description
===========



Updates an existing policy with a new name, description, or content. If any parameter is not supplied, that value remains unchanged. Note that you cannot change a policy's type.

 

This operation can be called only from the organization's master account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/organizations-2016-11-28/UpdatePolicy>`_


========
Synopsis
========

::

    update-policy
  --policy-id <value>
  [--name <value>]
  [--description <value>]
  [--content <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--policy-id`` (string)


  The unique identifier (ID) of the policy that you want to update.

   

  The `regex pattern <http://wikipedia.org/wiki/regex>`_ for a policy ID string requires "p-" followed by from 8 to 128 lower-case letters or digits.

  

``--name`` (string)


  If provided, the new name for the policy.

   

  The `regex pattern <http://wikipedia.org/wiki/regex>`_ that is used to validate this parameter is a string of any of the characters in the ASCII character range.

  

``--description`` (string)


  If provided, the new description for the policy.

  

``--content`` (string)


  If provided, the new content for the policy. The text must be correctly formatted JSON that complies with the syntax for the policy's type. For more information, see `Service Control Policy Syntax <http://docs.aws.amazon.com/organizations/latest/userguide/orgs_reference_scp-syntax.html>`_ in the *AWS Organizations User Guide* .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To rename a policy and give it a new description**

The following example shows how to rename a policy and give it a new description. The output confirms the new name and description text. 

Command::

  aws organizations update-policy --policy-id p-examplepolicyid111 --name Renamed-Policy --description "This description replaces the original."
  
The output confirms the new name and description text.

Output::

  {
    "Policy": {
      "Content": "{ \"Version\": \"2012-10-17\", \"Statement\": { \"Effect\": \"Allow\", \"Action\": \"ec2:*\", \"Resource\": \"*\" } }",
      "PolicySummary": {
        "Id": "p-examplepolicyid111",
        "AwsManaged": false,
        "Arn":"arn:aws:organizations::111111111111:policy/o-exampleorgid/service_control_policy/p-examplepolicyid111",
        "Description": "This description replaces the original.",
        "Name": "Renamed-Policy",
        "Type": "SERVICE_CONTROL_POLICY"
      }
    }
  }
  
**To change the JSON text associated with an SCP**

The following example shows how to replace the JSON text of the SCP in the preceding example with a new JSON policy text string that allows S3 actions instead of EC2 actions. 

Command::

  aws organizations update-policy --policy-id p-examplepolicyid111 --content file://policy-content.json
  
The file ``policy-content.json`` is a JSON document in the current folder that contains the following text::
  
  { 
    "Version": "2012-10-17",
    "Statement": { 
      "Effect": "Allow",
      "Action": "s3:*",
      "Resource": "*" 
    } 
  }

The output confirms the updated JSON text.

Output::

  {
    "Policy": {
      "Content": "{ \"Version\": \"2012-10-17\", \"Statement\": { \"Effect\": \"Allow\", \"Action\": \"s3:*\", \"Resource\": \"*\" } }",
      "PolicySummary": {    
        "Arn": "arn:aws:organizations::111111111111:policy/o-exampleorgid/service_control_policy/p-examplepolicyid111",
        "AwsManaged": false;
        "Description": "This description replaces the original.",
        "Id": "p-examplepolicyid111",
        "Name": "Renamed-Policy",
        "Type": "SERVICE_CONTROL_POLICY"
      }
    }

======
Output
======

Policy -> (structure)

  

  A structure that contains details about the updated policy, showing the requested changes.

  

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

    

    

  

