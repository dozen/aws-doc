[ :ref:`aws <cli:aws>` . :ref:`sts <cli:aws sts>` ]

.. _cli:aws sts assume-role:


***********
assume-role
***********



===========
Description
===========



Returns a set of temporary security credentials (consisting of an access key ID, a secret access key, and a security token) that you can use to access AWS resources that you might not normally have access to. Typically, you use ``assume-role`` for cross-account access or federation. For a comparison of ``assume-role`` with the other APIs that produce temporary credentials, see `Requesting Temporary Security Credentials <http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp_request.html>`_ and `Comparing the AWS STS APIs <http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp_request.html#stsapi_comparison>`_ in the *IAM User Guide* .

 

 **Important:** You cannot call ``assume-role`` by using AWS root account credentials; access is denied. You must use credentials for an IAM user or an IAM role to call ``assume-role`` . 

 

For cross-account access, imagine that you own multiple accounts and need to access resources in each account. You could create long-term credentials in each account to access those resources. However, managing all those credentials and remembering which one can access which account can be time consuming. Instead, you can create one set of long-term credentials in one account and then use temporary security credentials to access all the other accounts by assuming roles in those accounts. For more information about roles, see `IAM Roles (Delegation and Federation) <http://docs.aws.amazon.com/IAM/latest/UserGuide/roles-toplevel.html>`_ in the *IAM User Guide* . 

 

For federation, you can, for example, grant single sign-on access to the AWS Management Console. If you already have an identity and authentication system in your corporate network, you don't have to recreate user identities in AWS in order to grant those user identities access to AWS. Instead, after a user has been authenticated, you call ``assume-role`` (and specify the role with the appropriate permissions) to get temporary security credentials for that user. With those temporary security credentials, you construct a sign-in URL that users can use to access the console. For more information, see `Common Scenarios for Temporary Credentials <http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp.html#sts-introduction>`_ in the *IAM User Guide* .

 

The temporary security credentials are valid for the duration that you specified when calling ``assume-role`` , which can be from 900 seconds (15 minutes) to a maximum of 3600 seconds (1 hour). The default is 1 hour. 

 

The temporary security credentials created by ``assume-role`` can be used to make API calls to any AWS service with the following exception: you cannot call the STS service's ``get-federation-token`` or ``get-session-token`` APIs.

 

Optionally, you can pass an IAM access policy to this operation. If you choose not to pass a policy, the temporary security credentials that are returned by the operation have the permissions that are defined in the access policy of the role that is being assumed. If you pass a policy to this operation, the temporary security credentials that are returned by the operation have the permissions that are allowed by both the access policy of the role that is being assumed, * **and** * the policy that you pass. This gives you a way to further restrict the permissions for the resulting temporary security credentials. You cannot use the passed policy to grant permissions that are in excess of those allowed by the access policy of the role that is being assumed. For more information, see `Permissions for AssumeRole, AssumeRoleWithSAML, and assume-role-with-web-identity <http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp_control-access_assumerole.html>`_ in the *IAM User Guide* .

 

To assume a role, your AWS account must be trusted by the role. The trust relationship is defined in the role's trust policy when the role is created. That trust policy states which accounts are allowed to delegate access to this account's role.

 

The user who wants to access the role must also have permissions delegated from the role's administrator. If the user is in a different account than the role, then the user's administrator must attach a policy that allows the user to call assume-role on the ARN of the role in the other account. If the user is in the same account as the role, then you can either attach a policy to the user (identical to the previous different account user), or you can add the user as a principal directly in the role's trust policy

 

 **Using MFA with assume-role**  

 

You can optionally include multi-factor authentication (MFA) information when you call ``assume-role`` . This is useful for cross-account scenarios in which you want to make sure that the user who is assuming the role has been authenticated using an AWS MFA device. In that scenario, the trust policy of the role being assumed includes a condition that tests for MFA authentication; if the caller does not include valid MFA information, the request to assume the role is denied. The condition in a trust policy that tests for MFA authentication might look like the following example.

 

 ``"Condition": {"Bool": {"aws:MultiFactorAuthPresent": true}}``  

 

For more information, see `Configuring MFA-Protected API Access <http://docs.aws.amazon.com/IAM/latest/UserGuide/MFAProtectedAPI.html>`_ in the *IAM User Guide* guide.

 

To use MFA with ``assume-role`` , you pass values for the ``SerialNumber`` and ``TokenCode`` parameters. The ``SerialNumber`` value identifies the user's hardware or virtual MFA device. The ``TokenCode`` is the time-based one-time password (TOTP) that the MFA devices produces. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sts-2011-06-15/AssumeRole>`_


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
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--role-arn`` (string)


  The Amazon Resource Name (ARN) of the role to assume.

  

``--role-session-name`` (string)


  An identifier for the assumed role session.

   

  Use the role session name to uniquely identify a session when the same role is assumed by different principals or for different reasons. In cross-account scenarios, the role session name is visible to, and can be logged by the account that owns the role. The role session name is also used in the ARN of the assumed role principal. This means that subsequent cross-account API requests using the temporary security credentials will expose the role session name to the external account in their CloudTrail logs.

   

  The regex used to validate this parameter is a string of characters consisting of upper- and lower-case alphanumeric characters with no spaces. You can also include underscores or any of the following characters: =,.@-

  

``--policy`` (string)


  An IAM policy in JSON format.

   

  This parameter is optional. If you pass a policy, the temporary security credentials that are returned by the operation have the permissions that are allowed by both (the intersection of) the access policy of the role that is being assumed, *and* the policy that you pass. This gives you a way to further restrict the permissions for the resulting temporary security credentials. You cannot use the passed policy to grant permissions that are in excess of those allowed by the access policy of the role that is being assumed. For more information, see `Permissions for AssumeRole, AssumeRoleWithSAML, and assume-role-with-web-identity <http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp_control-access_assumerole.html>`_ in the *IAM User Guide* .

   

  The format for this parameter, as described by its regex pattern, is a string of characters up to 2048 characters in length. The characters can be any ASCII character from the space character to the end of the valid character list (\u0020-\u00FF). It can also include the tab (\u0009), linefeed (\u000A), and carriage return (\u000D) characters.

   

  .. note::

     

    The policy plain text must be 2048 bytes or shorter. However, an internal conversion compresses it into a packed binary format with a separate limit. The PackedPolicySize response element indicates by percentage how close to the upper size limit the policy is, with 100% equaling the maximum allowed size.

     

  

``--duration-seconds`` (integer)


  The duration, in seconds, of the role session. The value can range from 900 seconds (15 minutes) to 3600 seconds (1 hour). By default, the value is set to 3600 seconds.

   

  .. note::

     

    This is separate from the duration of a console session that you might request using the returned credentials. The request to the federation endpoint for a console sign-in token takes a ``SessionDuration`` parameter that specifies the maximum length of the console session, separately from the ``DurationSeconds`` parameter on this API. For more information, see `Creating a URL that Enables Federated Users to Access the AWS Management Console <http://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_providers_enable-console-custom-url.html>`_ in the *IAM User Guide* .

     

  

``--external-id`` (string)


  A unique identifier that is used by third parties when assuming roles in their customers' accounts. For each role that the third party can assume, they should instruct their customers to ensure the role's trust policy checks for the external ID that the third party generated. Each time the third party assumes the role, they should pass the customer's external ID. The external ID is useful in order to help third parties bind a role to the customer who created it. For more information about the external ID, see `How to Use an External ID When Granting Access to Your AWS Resources to a Third Party <http://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_create_for-user_externalid.html>`_ in the *IAM User Guide* .

   

  The regex used to validated this parameter is a string of characters consisting of upper- and lower-case alphanumeric characters with no spaces. You can also include underscores or any of the following characters: =,.@:/-

  

``--serial-number`` (string)


  The identification number of the MFA device that is associated with the user who is making the ``assume-role`` call. Specify this value if the trust policy of the role being assumed includes a condition that requires MFA authentication. The value is either the serial number for a hardware device (such as ``GAHT12345678`` ) or an Amazon Resource Name (ARN) for a virtual device (such as ``arn:aws:iam::123456789012:mfa/user`` ).

   

  The regex used to validate this parameter is a string of characters consisting of upper- and lower-case alphanumeric characters with no spaces. You can also include underscores or any of the following characters: =,.@-

  

``--token-code`` (string)


  The value provided by the MFA device, if the trust policy of the role being assumed requires MFA (that is, if the policy includes a condition that tests for MFA). If the role being assumed requires MFA and if the ``TokenCode`` value is missing or expired, the ``assume-role`` call returns an "access denied" error.

   

  The format for this parameter, as described by its regex pattern, is a sequence of six numeric digits.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

To assume a role::

  aws sts assume-role --role-arn arn:aws:iam::123456789012:role/xaccounts3access --role-session-name s3-access-example

The output of the command contains an access key, secret key, and session token that you can use to authenticate to AWS::

  {
      "AssumedRoleUser": {
          "AssumedRoleId": "AROA3XFRBF535PLBIFPI4:s3-access-example",
          "Arn": "arn:aws:sts::123456789012:assumed-role/xaccounts3access/s3-access-example"
      },
      "Credentials": {
          "SecretAccessKey": "9drTJvcXLB89EXAMPLELB8923FB892xMFI",
          "SessionToken": "AQoXdzELDDY//////////wEaoAK1wvxJY12r2IrDFT2IvAzTCn3zHoZ7YNtpiQLF0MqZye/qwjzP2iEXAMPLEbw/m3hsj8VBTkPORGvr9jM5sgP+w9IZWZnU+LWhmg+a5fDi2oTGUYcdg9uexQ4mtCHIHfi4citgqZTgco40Yqr4lIlo4V2b2Dyauk0eYFNebHtYlFVgAUj+7Indz3LU0aTWk1WKIjHmmMCIoTkyYp/k7kUG7moeEYKSitwQIi6Gjn+nyzM+PtoA3685ixzv0R7i5rjQi0YE0lf1oeie3bDiNHncmzosRM6SFiPzSvp6h/32xQuZsjcypmwsPSDtTPYcs0+YN/8BRi2/IcrxSpnWEXAMPLEXSDFTAQAM6Dl9zR0tXoybnlrZIwMLlMi1Kcgo5OytwU=",
          "Expiration": "2016-03-15T00:05:07Z",
          "AccessKeyId": "ASIAJEXAMPLEXEG2JICEA"
      }
  }

For AWS CLI use, you can set up a named profile associated with a role. When you use the profile, the AWS CLI will call assume-role and manage credentials for you. See `Assuming a Role`_ in the *AWS CLI User Guide* for instructions.

.. _`Assuming a Role`: http://docs.aws.amazon.com/cli/latest/userguide/cli-roles.html

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

    

    The ARN of the temporary security credentials that are returned from the  assume-role action. For more information about ARNs and how to use them in policies, see `IAM Identifiers <http://docs.aws.amazon.com/IAM/latest/UserGuide/reference_identifiers.html>`_ in *Using IAM* . 

    

    

  

PackedPolicySize -> (integer)

  

  A percentage value that indicates the size of the policy in packed form. The service rejects any policy with a packed size greater than 100 percent, which means the policy exceeded the allowed space.

  

  

