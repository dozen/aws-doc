[ :ref:`aws <cli:aws>` . :ref:`organizations <cli:aws organizations>` ]

.. _cli:aws organizations describe-organization:


*********************
describe-organization
*********************



===========
Description
===========



Retrieves information about the organization that the user's account belongs to.

 

This operation can be called from any account in the organization.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/organizations-2016-11-28/DescribeOrganization>`_


========
Synopsis
========

::

    describe-organization
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get details about an organization**

The following example shows how to request information about the current user's organization.

Command::

  aws organizations describe-organization
  
Output::

  {
    "Organization": {
      "MasterAccountArn": "arn:aws:organizations::111111111111:account/o-exampleorgid/111111111111",
      "MasterAccountEmail": "bill@example.com",
      "MasterAccountId": "111111111111",
      "Id": "o-exampleorgid",
      "FeatureSet": "ALL",
      "Arn": "arn:aws:organizations::111111111111:organization/o-exampleorgid",
      "AvailablePolicyTypes": [
        {
          "Status": "ENABLED",
          "Type": "SERVICE_CONTROL_POLICY"
      ]
    }
  }

======
Output
======

Organization -> (structure)

  

  A structure that contains information about the organization.

  

  Id -> (string)

    

    The unique identifier (ID) of an organization.

     

    The `regex pattern <http://wikipedia.org/wiki/regex>`_ for an organization ID string requires "o-" followed by from 10 to 32 lower-case letters or digits.

    

    

  Arn -> (string)

    

    The Amazon Resource Name (ARN) of an organization.

     

    For more information about ARNs in Organizations, see `ARN Formats Supported by Organizations <http://docs.aws.amazon.com/organizations/latest/userguide/orgs_permissions.html#orgs-permissions-arns>`_ in the *AWS Organizations User Guide* .

    

    

  FeatureSet -> (string)

    

    Specifies the functionality that currently is available to the organization. If set to "ALL", then all features are enabled and policies can be applied to accounts in the organization. If set to "CONSOLIDATED_BILLING", then only consolidated billing functionality is available. For more information, see `Enabling All Features in Your Organization <http://docs.aws.amazon.com/IAM/latest/UserGuide/orgs_manage_org_support-all-features.html>`_ in the *AWS Organizations User Guide* .

    

    

  MasterAccountArn -> (string)

    

    The Amazon Resource Name (ARN) of the account that is designated as the master account for the organization.

     

    For more information about ARNs in Organizations, see `ARN Formats Supported by Organizations <http://docs.aws.amazon.com/organizations/latest/userguide/orgs_permissions.html#orgs-permissions-arns>`_ in the *AWS Organizations User Guide* .

    

    

  MasterAccountId -> (string)

    

    The unique identifier (ID) of the master account of an organization.

     

    The `regex pattern <http://wikipedia.org/wiki/regex>`_ for an account ID string requires exactly 12 digits.

    

    

  MasterAccountEmail -> (string)

    

    The email address that is associated with the AWS account that is designated as the master account for the organization.

    

    

  AvailablePolicyTypes -> (list)

    

    A list of policy types that are enabled for this organization. For example, if your organization has all features enabled, then service control policies (SCPs) are included in the list.

    

    (structure)

      

      Contains information about a policy type and its status in the associated root.

      

      Type -> (string)

        

        The name of the policy type.

        

        

      Status -> (string)

        

        The status of the policy type as it relates to the associated root. To attach a policy of the specified type to a root or to an OU or account in that root, it must be available in the organization and enabled for that root.

        

        

      

    

  

