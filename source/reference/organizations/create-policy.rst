[ :ref:`aws <cli:aws>` . :ref:`organizations <cli:aws organizations>` ]

.. _cli:aws organizations create-policy:


*************
create-policy
*************



===========
Description
===========



Creates a policy of a specified type that you can attach to a root, an organizational unit (OU), or an individual AWS account.

 

For more information about policies and their use, see `Managing Organization Policies <http://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies.html>`_ .

 

This operation can be called only from the organization's master account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/organizations-2016-11-28/CreatePolicy>`_


========
Synopsis
========

::

    create-policy
  --content <value>
  --description <value>
  --name <value>
  --type <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--content`` (string)


  The policy content to add to the new policy. For example, if you create a `service control policy <http://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scp.html>`_ (SCP), this string must be JSON text that specifies the permissions that admins in attached accounts can delegate to their users, groups, and roles. For more information about the SCP syntax, see `Service Control Policy Syntax <http://docs.aws.amazon.com/organizations/latest/userguide/orgs_reference_scp-syntax.html>`_ in the *AWS Organizations User Guide* .

  

``--description`` (string)


  An optional description to assign to the policy.

  

``--name`` (string)


  The friendly name to assign to the policy.

   

  The `regex pattern <http://wikipedia.org/wiki/regex>`_ that is used to validate this parameter is a string of any of the characters in the ASCII character range.

  

``--type`` (string)


  The type of policy to create.

   

  .. note::

     

    In the current release, the only type of policy that you can create is a service control policy (SCP).

     

  

  Possible values:

  
  *   ``SERVICE_CONTROL_POLICY``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create an SCP**

The following example shows how to create a service control policy (SCP) that is named AllowAllS3Actions. In this example, we pass the new content as a reference to a file that has the new text.

Command::

  aws organizations create-policy --type SERVICE_CONTROL_POLICY --description "Enables admins of attached accounts to delegate all S3 permissions" --name AllowAllS3Actions --content file://policy-content.json

The file ``policy-content.json`` is a JSON document in the current folder that contains the following text::
  
  {
    "Version": "2012-10-17",
    "Statement": {
      "Effect": "Allow",
      "Action": "s3:*"
    }
  }

The output includes a Policy structure that contains details about the new policy.

Output::

  {
    "Policy": {
      "Content": "{\"Version\":\"2012-10-17\",\"Statement\":{\"Effect\":\"Allow\",\"Action\":\"s3:*\"}}",
      "PolicySummary": {
        "Arn": "arn:aws:organizations::o-exampleorgid:policy/service_control_policy/p-examplepolicyid111",
        "Description": "Enables admins of attached accounts to delegate all S3 permissions",
        "Name": "AllowAllS3Actions",
        "Type":"SERVICE_CONTROL_POLICY"
      }
    }
  }
  
For more information about creating and using policies in your organization, see `Managing Organization Policies`_ in the *AWS Organizations User Guide*.

.. _`Managing Organization Policies`: http://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies.html

======
Output
======

Policy -> (structure)

  

  A structure that contains details about the newly created policy.

  

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

    

    

  

