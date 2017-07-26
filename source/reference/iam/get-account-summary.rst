[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam get-account-summary:


*******************
get-account-summary
*******************



===========
Description
===========



Retrieves information about IAM entity usage and IAM quotas in the AWS account.

 

For information about limitations on IAM entities, see `Limitations on IAM Entities`_ in the *IAM User Guide* . 



========
Synopsis
========

::

    get-account-summary
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To get information about IAM entity usage and IAM quotas in the current account**

The following ``get-account-summary`` command returns information about the current IAM entity usage and current IAM entity quotas in the account::

  aws iam get-account-summary

Output::

  {
    "SummaryMap": {
        "UsersQuota": 5000,
        "GroupsQuota": 100,
        "InstanceProfiles": 6,
        "SigningCertificatesPerUserQuota": 2,
        "AccountAccessKeysPresent": 0,
        "RolesQuota": 250,
        "RolePolicySizeQuota": 10240,
        "AccountSigningCertificatesPresent": 0,
        "Users": 27,
        "ServerCertificatesQuota": 20,
        "ServerCertificates": 0,
        "AssumeRolePolicySizeQuota": 2048,
        "Groups": 7,
        "MFADevicesInUse": 1,
        "Roles": 3,
        "AccountMFAEnabled": 1,
        "MFADevices": 3,
        "GroupsPerUserQuota": 10,
        "GroupPolicySizeQuota": 5120,
        "InstanceProfilesQuota": 100,
        "AccessKeysPerUserQuota": 2,
        "Providers": 0,
        "UserPolicySizeQuota": 2048
    }
  }

For more information about entity limitations, see `Limitations on IAM Entities`_ in the *Using IAM* guide.

.. _`Limitations on IAM Entities`: http://docs.aws.amazon.com/IAM/latest/UserGuide/LimitationsOnEntities.html


======
Output
======

SummaryMap -> (map)

  

  A set of key value pairs containing information about IAM entity usage and IAM quotas.

   

   ``SummaryMap`` contains the following keys: 

   
  * **AccessKeysPerUserQuota**  The maximum number of active access keys allowed for each IAM user. 
   
  * **AccountAccessKeysPresent**  This value is 1 if the AWS account (root) has an access key, otherwise it is 0. 
   
  * **AccountMFAEnabled**  This value is 1 if the AWS account (root) has an MFA device assigned, otherwise it is 0. 
   
  * **AccountSigningCertificatesPresent**  This value is 1 if the AWS account (root) has a signing certificate, otherwise it is 0. 
   
  * **AssumeRolePolicySizeQuota**  The maximum allowed size for assume role policy documents (trust policies), in non-whitespace characters. 
   
  * **AttachedPoliciesPerGroupQuota**  The maximum number of managed policies that can be attached to an IAM group.  
   
  * **AttachedPoliciesPerRoleQuota**  The maximum number of managed policies that can be attached to an IAM role.  
   
  * **AttachedPoliciesPerUserQuota**  The maximum number of managed policies that can be attached to an IAM user.  
   
  * **GroupPolicySizeQuota**  The maximum allowed size for the aggregate of all inline policies embedded in an IAM group, in non-whitespace characters.  
   
  * **Groups**  The number of IAM groups in the AWS account. 
   
  * **GroupsPerUserQuota**  The maximum number of IAM groups each IAM user can belong to.  
   
  * **GroupsQuota**  The maximum number of IAM groups allowed in the AWS account.  
   
  * **InstanceProfiles**  The number of instance profiles in the AWS account.  
   
  * **InstanceProfilesQuota**  The maximum number of instance profiles allowed in the AWS account.  
   
  * **MFADevices**  The number of MFA devices in the AWS account, including those assigned and unassigned.  
   
  * **MFADevicesInUse**  The number of MFA devices that have been assigned to an IAM user or to the AWS account (root).  
   
  * **Policies**  The number of customer managed policies in the AWS account.  
   
  * **PoliciesQuota**  The maximum number of customer managed policies allowed in the AWS account.  
   
  * **PolicySizeQuota**  The maximum allowed size of a customer managed policy, in non-whitespace characters.  
   
  * **PolicyVersionsInUse**  The number of managed policies that are attached to IAM users, groups, or roles in the AWS account.  
   
  * **PolicyVersionsInUseQuota**  The maximum number of managed policies that can be attached to IAM users, groups, or roles in the AWS account.  
   
  * **Providers**  The number of identity providers in the AWS account.  
   
  * **RolePolicySizeQuota**  The maximum allowed size for the aggregate of all inline policies (access policies, not the trust policy) embedded in an IAM role, in non-whitespace characters.  
   
  * **Roles**  The number of IAM roles in the AWS account.  
   
  * **RolesQuota**  The maximum number of IAM roles allowed in the AWS account.  
   
  * **ServerCertificates**  The number of server certificates in the AWS account.  
   
  * **ServerCertificatesQuota**  The maximum number of server certificates allowed in the AWS account.  
   
  * **SigningCertificatesPerUserQuota**  The maximum number of X.509 signing certificates allowed for each IAM user.  
   
  * **UserPolicySizeQuota**  The maximum allowed size for the aggregate of all inline policies embedded in an IAM user, in non-whitespace characters.  
   
  * **Users**  The number of IAM users in the AWS account.  
   
  * **UsersQuota**  The maximum number of IAM users allowed in the AWS account.  
   
  * **VersionsPerPolicyQuota**  The maximum number of policy versions allowed for each managed policy.  
   

   

  

  key -> (string)

    

    

  value -> (integer)

    

    

  



.. _Limitations on IAM Entities: http://docs.aws.amazon.com/IAM/latest/UserGuide/LimitationsOnEntities.html
