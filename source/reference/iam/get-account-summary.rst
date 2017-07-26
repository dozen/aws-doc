[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam get-account-summary:


*******************
get-account-summary
*******************



===========
Description
===========



Retrieves information about IAM entity usage and IAM quotas in the AWS account.

 

For information about limitations on IAM entities, see `Limitations on IAM Entities <http://docs.aws.amazon.com/IAM/latest/UserGuide/LimitationsOnEntities.html>`_ in the *IAM User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/iam-2010-05-08/GetAccountSummary>`_


========
Synopsis
========

::

    get-account-summary
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

  

  key -> (string)

    

    

  value -> (integer)

    

    

  

