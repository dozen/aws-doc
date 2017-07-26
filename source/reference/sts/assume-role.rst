[ :ref:`aws <cli:aws>` . :ref:`sts <cli:aws sts>` ]

.. _cli:aws sts assume-role:


***********
assume-role
***********



===========
Description
===========



Returns a set of temporary security credentials (consisting of an access key ID, a secret access key, and a security token) that you can use to access AWS resources that you might not normally have access to. Typically, you use ``assume-role`` for cross-account access or federation. 

 

**Important:** You cannot call ``assume-role`` by using AWS account credentials; access will be denied. You must use IAM user credentials or temporary security credentials to call ``assume-role`` . 

 

For cross-account access, imagine that you own multiple accounts and need to access resources in each account. You could create long-term credentials in each account to access those resources. However, managing all those credentials and remembering which one can access which account can be time consuming. Instead, you can create one set of long-term credentials in one account and then use temporary security credentials to access all the other accounts by assuming roles in those accounts. For more information about roles, see `IAM Roles (Delegation and Federation)`_ in the *Using IAM* . 

 

For federation, you can, for example, grant single sign-on access to the AWS Management Console. If you already have an identity and authentication system in your corporate network, you don't have to recreate user identities in AWS in order to grant those user identities access to AWS. Instead, after a user has been authenticated, you call ``assume-role`` (and specify the role with the appropriate permissions) to get temporary security credentials for that user. With those temporary security credentials, you construct a sign-in URL that users can use to access the console. For more information, see `Common Scenarios for Temporary Credentials`_ in the *Using IAM* .

 

The temporary security credentials are valid for the duration that you specified when calling ``assume-role`` , which can be from 900 seconds (15 minutes) to 3600 seconds (1 hour). The default is 1 hour. 

 

Optionally, you can pass an IAM access policy to this operation. If you choose not to pass a policy, the temporary security credentials that are returned by the operation have the permissions that are defined in the access policy of the role that is being assumed. If you pass a policy to this operation, the temporary security credentials that are returned by the operation have the permissions that are allowed by both the access policy of the role that is being assumed, ***and*** the policy that you pass. This gives you a way to further restrict the permissions for the resulting temporary security credentials. You cannot use the passed policy to grant permissions that are in excess of those allowed by the access policy of the role that is being assumed. For more information, see `Permissions for AssumeRole, AssumeRoleWithSAML, and assume-role-with-web-identity`_ in the *Using IAM* .

 

To assume a role, your AWS account must be trusted by the role. The trust relationship is defined in the role's trust policy when the role is created. You must also have a policy that allows you to call ``sts:AssumeRole`` . 

 

 **Using MFA with assume-role**  

 

You can optionally include multi-factor authentication (MFA) information when you call ``assume-role`` . This is useful for cross-account scenarios in which you want to make sure that the user who is assuming the role has been authenticated using an AWS MFA device. In that scenario, the trust policy of the role being assumed includes a condition that tests for MFA authentication; if the caller does not include valid MFA information, the request to assume the role is denied. The condition in a trust policy that tests for MFA authentication might look like the following example.

 

 ``"Condition": {"Bool": {"aws:MultiFactorAuthPresent": true}}``  

 

For more information, see `Configuring MFA-Protected API Access`_ in the *Using IAM* guide.

 

To use MFA with ``assume-role`` , you pass values for the ``SerialNumber`` and ``TokenCode`` parameters. The ``SerialNumber`` value identifies the user's hardware or virtual MFA device. The ``TokenCode`` is the time-based one-time password (TOTP) that the MFA devices produces. 

     

========
Synopsis
========

::

    assume-role
  --role-arn <value>
  --role-session-name <value>
  [--policy <value>]
  [--duration-seconds <value>]
  [--external-id <value>]
  [--serial-number <value>]
  [--token-code <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--role-arn`` (string)


  The Amazon Resource Name (ARN) of the role to assume.

  

``--role-session-name`` (string)


  An identifier for the assumed role session. 

   

  Use the role session name to uniquely identify a session when the same role is assumed by different principals or for different reasons. In cross-account scenarios, the role session name is visible to, and can be logged by the account that owns the role. The role session name is also used in the ARN of the assumed role principal. This means that subsequent cross-account API requests using the temporary security credentials will expose the role session name to the external account in their CloudTrail logs.

  

``--policy`` (string)


  An IAM policy in JSON format.

   

  This parameter is optional. If you pass a policy, the temporary security credentials that are returned by the operation have the permissions that are allowed by both (the intersection of) the access policy of the role that is being assumed, *and* the policy that you pass. This gives you a way to further restrict the permissions for the resulting temporary security credentials. You cannot use the passed policy to grant permissions that are in excess of those allowed by the access policy of the role that is being assumed. For more information, see `Permissions for AssumeRole, AssumeRoleWithSAML, and assume-role-with-web-identity`_ in the *Using IAM* .

   

  .. note::

    The policy plain text must be 2048 bytes or shorter. However, an internal conversion compresses it into a packed binary format with a separate limit. The PackedPolicySize response element indicates by percentage how close to the upper size limit the policy is, with 100% equaling the maximum allowed size.

  

``--duration-seconds`` (integer)


  The duration, in seconds, of the role session. The value can range from 900 seconds (15 minutes) to 3600 seconds (1 hour). By default, the value is set to 3600 seconds. 

  

``--external-id`` (string)


  A unique identifier that is used by third parties when assuming roles in their customers' accounts. For each role that the third party can assume, they should instruct their customers to ensure the role's trust policy checks for the external ID that the third party generated. Each time the third party assumes the role, they should pass the customer's external ID. The external ID is useful in order to help third parties bind a role to the customer who created it. For more information about the external ID, see `How to Use an External ID When Granting Access to Your AWS Resources to a Third Party`_ in the *Using IAM* .

  

``--serial-number`` (string)


  The identification number of the MFA device that is associated with the user who is making the ``assume-role`` call. Specify this value if the trust policy of the role being assumed includes a condition that requires MFA authentication. The value is either the serial number for a hardware device (such as ``GAHT12345678`` ) or an Amazon Resource Name (ARN) for a virtual device (such as ``arn:aws:iam::123456789012:mfa/user`` ).

  

``--token-code`` (string)


  The value provided by the MFA device, if the trust policy of the role being assumed requires MFA (that is, if the policy includes a condition that tests for MFA). If the role being assumed requires MFA and if the ``TokenCode`` value is missing or expired, the ``assume-role`` call returns an "access denied" error.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

Credentials -> (structure)

  

  The temporary security credentials, which include an access key ID, a secret access key, and a security (or session) token.

   

  **Note:** The size of the security token that STS APIs return is not fixed. We strongly recommend that you make no assumptions about the maximum size. As of this writing, the typical size is less than 4096 bytes, but that can vary. Also, future updates to AWS might require larger sizes.

  

  AccessKeyId -> (string)

    

    The access key ID that identifies the temporary security credentials.

    

    

  SecretAccessKey -> (string)

    

    The secret access key that can be used to sign requests.

    

    

  SessionToken -> (string)

    

    The token that users must pass to the service API to use the temporary credentials.

    

    

  Expiration -> (timestamp)

    

    The date on which the current credentials expire.

    

    

  

AssumedRoleUser -> (structure)

  

  The Amazon Resource Name (ARN) and the assumed role ID, which are identifiers that you can use to refer to the resulting temporary security credentials. For example, you can reference these credentials as a principal in a resource-based policy by using the ARN or assumed role ID. The ARN and ID include the ``RoleSessionName`` that you specified when you called ``assume-role`` . 

  

  AssumedRoleId -> (string)

    

    A unique identifier that contains the role ID and the role session name of the role that is being assumed. The role ID is generated by AWS when the role is created.

    

    

  Arn -> (string)

    

    The ARN of the temporary security credentials that are returned from the  assume-role action. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in *Using IAM* . 

    

    

  

PackedPolicySize -> (integer)

  

  A percentage value that indicates the size of the policy in packed form. The service rejects any policy with a packed size greater than 100 percent, which means the policy exceeded the allowed space. 

  

  



.. _IAM Roles (Delegation and Federation): http://docs.aws.amazon.com/IAM/latest/UserGuide/roles-toplevel.html
.. _How to Use an External ID When Granting Access to Your AWS Resources to a Third Party: http://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_create_for-user_externalid.html
.. _Configuring MFA-Protected API Access: http://docs.aws.amazon.com/IAM/latest/UserGuide/MFAProtectedAPI.html
.. _IAM Identifiers: http://docs.aws.amazon.com/IAM/latest/UserGuide/reference_identifiers.html
.. _Permissions for AssumeRole, AssumeRoleWithSAML, and assume-role-with-web-identity: http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp_control-access_assumerole.html
.. _Common Scenarios for Temporary Credentials: http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp.html#sts-introduction
