[ :ref:`aws <cli:aws>` . :ref:`organizations <cli:aws organizations>` ]

.. _cli:aws organizations create-organization:


*******************
create-organization
*******************



===========
Description
===========



Creates an AWS organization. The account whose user is calling the create-organization operation automatically becomes the `master account <http://docs.aws.amazon.com/IAM/latest/UserGuide/orgs_getting-started_concepts.html#account>`_ of the new organization.

 

This operation must be called using credentials from the account that is to become the new organization's master account. The principal must also have the relevant IAM permissions.

 

By default (or if you set the ``FeatureSet`` parameter to ``ALL`` ), the new organization is created with all features enabled and service control policies automatically enabled in the root. If you instead choose to create the organization supporting only the consolidated billing features by setting the ``FeatureSet`` parameter to ``CONSOLIDATED_BILLING"`` , then no policy types are enabled by default and you cannot use organization policies.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/organizations-2016-11-28/CreateOrganization>`_


========
Synopsis
========

::

    create-organization
  [--feature-set <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--feature-set`` (string)


  Specifies the feature set supported by the new organization. Each feature set supports different levels of functionality.

   

   
  * *CONSOLIDATED_BILLING* : All member accounts have their bills consolidated to and paid by the master account. For more information, see `Consolidated Billing <http://docs.aws.amazon.com/organizations/latest/userguide/orgs_getting-started_concepts.html#feature-set-cb-only>`_ in the *AWS Organizations User Guide* . 
   
  * *ALL* : In addition to all the features supported by the consolidated billing feature set, the master account can also apply any type of policy to any member account in the organization. For more information, see `All features <http://docs.aws.amazon.com/organizations/latest/userguide/orgs_getting-started_concepts.html#feature-set-all>`_ in the *AWS Organizations User Guide* . 
   

  

  Possible values:

  
  *   ``ALL``

  
  *   ``CONSOLIDATED_BILLING``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create an organization with all features enabled**

Bill wants to create an organization using credentials from account 111111111111. The following example shows that the account becomes the master account in the new organization. Because he does not specify a features set, the new organization defaults to all features enabled and service control policies are enabled on the root.

Command::

  aws organizations create-organization

The output includes an Organization structure that shows that the FeatureSet is ALL, and that the SCP policy type is enabled

Output::

  {
    "Organization": {
      "AvailablePolicyTypes": [
        {
          "Status": "ENABLED",
          "Type": "SERVICE_CONTROL_POLICY"
        }
      ],
      "MasterAccountId": "111111111111",
      "MasterAccountArn": "arn:aws:organizations::111111111111:account/o-exampleorgid/111111111111",
      "MasterAccountEmail": "bill@example.com",
      "FeatureSet": "ALL",
      "Id": "o-exampleorgid",
      "Arn": "arn:aws:organizations::111111111111:organization/o-exampleorgid"
    }
  }

**To create an organization with only consolidated billing features enabled**

The following example creates an organization that supports only the consolidated billing features

Command::

  aws organizations create-organization --feature-set CONSOLIDATED_BILLING

The output includes an Organization structure that shows that the FeatureSet includes only CONSOLIDATED_BILLING, and that there are no policy types enabled.

Output::

	{
	  "Organization": {
		"Arn": "arn:aws:organizations::111111111111:organization/o-exampleorgid",
		"AvailablePolicyTypes": [],
		"Id": "o-exampleorgid",
		"MasterAccountArn": "arn:aws:organizations::111111111111:account/o-exampleorgid/111111111111",
		"MasterAccountEmail": "bill@example.com",
		"MasterAccountId": "111111111111",
		"FeatureSet": "CONSOLIDATED_BILLING"
	  }
	}
  
For more information, see `Creating an Organization` in the *AWS Organizations Users Guide*.

.. _`Creating an Organization`: http://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_create.html

======
Output
======

Organization -> (structure)

  

  A structure that contains details about the newly created organization.

  

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

        

        

      

    

  

