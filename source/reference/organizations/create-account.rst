[ :ref:`aws <cli:aws>` . :ref:`organizations <cli:aws organizations>` ]

.. _cli:aws organizations create-account:


**************
create-account
**************



===========
Description
===========



Creates an AWS account that is automatically a member of the organization whose credentials made the request. This is an asynchronous request that AWS performs in the background. If you want to check the status of the request later, you need the ``OperationId`` response element from this operation to provide as a parameter to the  describe-create-account-status operation.

 

AWS Organizations preconfigures the new member account with a role (named ``OrganizationAccountAccessRole`` by default) that grants administrator permissions to the new account. Principals in the master account can assume the role. AWS Organizations clones the company name and address information for the new account from the organization's master account.

 

For more information about creating accounts, see `Creating an AWS Account in Your Organization <http://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_accounts_create.html>`_ in the *AWS Organizations User Guide* .

 

.. warning::

   

  You cannot remove accounts that are created with this operation from an organization. That also means that you cannot delete an organization that contains an account that is created with this operation.

   

 

.. note::

   

  When you create a member account with this operation, you can choose whether to create the account with the **IAM User and Role Access to Billing Information** switch enabled. If you enable it, IAM users and roles that have appropriate permissions can view billing information for the account. If you disable this, then only the account root user can access billing information. For information about how to disable this for an account, see `Granting Access to Your Billing Information and Tools <http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/grantaccess.html>`_ .

   

 

This operation can be called only from the organization's master account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/organizations-2016-11-28/CreateAccount>`_


========
Synopsis
========

::

    create-account
  --email <value>
  --account-name <value>
  [--role-name <value>]
  [--iam-user-access-to-billing <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--email`` (string)


  The email address of the owner to assign to the new member account. This email address must not already be associated with another AWS account.

  

``--account-name`` (string)


  The friendly name of the member account.

  

``--role-name`` (string)


  (Optional)

   

  The name of an IAM role that Organizations automatically preconfigures in the new member account. This role trusts the master account, allowing users in the master account to assume the role, as permitted by the master account administrator. The role has administrator permissions in the new member account.

   

  If you do not specify this parameter, the role name defaults to ``OrganizationAccountAccessRole`` .

   

  For more information about how to use this role to access the member account, see `Accessing and Administering the Member Accounts in Your Organization <http://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_accounts_access.html#orgs_manage_accounts_create-cross-account-role>`_ in the *AWS Organizations User Guide* , and steps 2 and 3 in `Tutorial\: Delegate Access Across AWS Accounts Using IAM Roles <http://docs.aws.amazon.com/IAM/latest/UserGuide/tutorial_cross-account-with-roles.html>`_ in the *IAM User Guide* .

   

  The `regex pattern <http://wikipedia.org/wiki/regex>`_ that is used to validate this parameter is a string of characters that can consist of uppercase letters, lowercase letters, digits with no spaces, and any of the following characters: =,.@-

  

``--iam-user-access-to-billing`` (string)


  If set to ``ALLOW`` , the new account enables IAM users to access account billing information *if* they have the required permissions. If set to ``DENY`` , then only the root user of the new account can access account billing information. For more information, see `Activating Access to the Billing and Cost Management Console <http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/grantaccess.html#ControllingAccessWebsite-Activate>`_ in the *AWS Billing and Cost Management User Guide* .

   

  If you do not specify this parameter, the value defaults to ALLOW, and IAM users and roles with the required permissions can access billing information for the new account.

  

  Possible values:

  
  *   ``ALLOW``

  
  *   ``DENY``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create an account**

The following example shows how to create a member account in an organization. The member account is configured with the name Production Account and the email address of susan@example.com. Organizations automatically creates an IAM role using the default name of OrganizationAccountAccessRole because the roleName parameter is not specified. Also, the setting that allows IAM users or roles with sufficient permissions to access account billing data is set to the default value of ALLOW because the IamUserAccessToBilling parameter is not specified. Organizations automatically sends Susan a "Welcome to AWS" email.

Command::

  aws organizations create-account --email susan@example.com --account-name "Production Account"

The output includes a structure that displays the ID of the request and its current status.

Output::

  {
    "CreateAccountStatus": {
      "State": "IN_PROGRESS",
      "Id": "car-examplecreateaccountrequestid111"
    }
  }

You can later query the current status of the request by providing the Id response value to the describe-create-account-status command as the value for the create-account-request-id parameter.
  
For more information, see `Creating an AWS Account in Your Organization` in the *AWS Organizations Users Guide*.

.. _`Creating an AWS Account in Your Organization`: http://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_accounts_create.html

======
Output
======

CreateAccountStatus -> (structure)

  

  A structure that contains details about the request to create an account. This response structure might not be fully populated when you first receive it because account creation is an asynchronous process. You can pass the returned CreateAccountStatus ID as a parameter to ``  describe-create-account-status `` to get status about the progress of the request at later times. 

  

  Id -> (string)

    

    The unique identifier (ID) that references this request. You get this value from the response of the initial  create-account request to create the account.

     

    The `regex pattern <http://wikipedia.org/wiki/regex>`_ for an create account request ID string requires "car-" followed by from 8 to 32 lower-case letters or digits.

    

    

  AccountName -> (string)

    

    The account name given to the account when it was created.

    

    

  State -> (string)

    

    The status of the request.

    

    

  RequestedTimestamp -> (timestamp)

    

    The date and time that the request was made for the account creation.

    

    

  CompletedTimestamp -> (timestamp)

    

    The date and time that the account was created and the request completed.

    

    

  AccountId -> (string)

    

    If the account was created successfully, the unique identifier (ID) of the new account.

     

    The `regex pattern <http://wikipedia.org/wiki/regex>`_ for an account ID string requires exactly 12 digits.

    

    

  FailureReason -> (string)

    

    If the request failed, a description of the reason for the failure.

     

     
    * ACCOUNT_LIMIT_EXCEEDED: The account could not be created because you have reached the limit on the number of accounts in your organization. 
     
    * EMAIL_ALREADY_EXISTS: The account could not be created because another AWS account with that email address already exists. 
     
    * INVALID_ADDRESS: The account could not be created because the address you provided is not valid. 
     
    * INVALID_EMAIL: The account could not be created because the email address you provided is not valid. 
     
    * INTERNAL_FAILURE: The account could not be created because of an internal failure. Try again later. If the problem persists, contact Customer Support. 
     

    

    

  

