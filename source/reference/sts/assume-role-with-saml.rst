[ :ref:`aws <cli:aws>` . :ref:`sts <cli:aws sts>` ]

.. _cli:aws sts assume-role-with-saml:


*********************
assume-role-with-saml
*********************



===========
Description
===========



Returns a set of temporary security credentials for users who have been authenticated via a SAML authentication response. This operation provides a mechanism for tying an enterprise identity store or directory to role-based AWS access without user-specific credentials or configuration. For a comparison of ``assume-role-with-saml`` with the other APIs that produce temporary credentials, see `Requesting Temporary Security Credentials <http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp_request.html>`_ and `Comparing the AWS STS APIs <http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp_request.html#stsapi_comparison>`_ in the *IAM User Guide* .

 

The temporary security credentials returned by this operation consist of an access key ID, a secret access key, and a security token. Applications can use these temporary security credentials to sign calls to AWS services.

 

The temporary security credentials are valid for the duration that you specified when calling ``assume-role`` , or until the time specified in the SAML authentication response's ``SessionNotOnOrAfter`` value, whichever is shorter. The duration can be from 900 seconds (15 minutes) to a maximum of 3600 seconds (1 hour). The default is 1 hour.

 

The temporary security credentials created by ``assume-role-with-saml`` can be used to make API calls to any AWS service with the following exception: you cannot call the STS service's ``get-federation-token`` or ``get-session-token`` APIs.

 

Optionally, you can pass an IAM access policy to this operation. If you choose not to pass a policy, the temporary security credentials that are returned by the operation have the permissions that are defined in the access policy of the role that is being assumed. If you pass a policy to this operation, the temporary security credentials that are returned by the operation have the permissions that are allowed by the intersection of both the access policy of the role that is being assumed, * **and** * the policy that you pass. This means that both policies must grant the permission for the action to be allowed. This gives you a way to further restrict the permissions for the resulting temporary security credentials. You cannot use the passed policy to grant permissions that are in excess of those allowed by the access policy of the role that is being assumed. For more information, see `Permissions for AssumeRole, AssumeRoleWithSAML, and assume-role-with-web-identity <http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp_control-access_assumerole.html>`_ in the *IAM User Guide* .

 

Before your application can call ``assume-role-with-saml`` , you must configure your SAML identity provider (IdP) to issue the claims required by AWS. Additionally, you must use AWS Identity and Access Management (IAM) to create a SAML provider entity in your AWS account that represents your identity provider, and create an IAM role that specifies this SAML provider in its trust policy. 

 

Calling ``assume-role-with-saml`` does not require the use of AWS security credentials. The identity of the caller is validated by using keys in the metadata document that is uploaded for the SAML provider entity for your identity provider. 

 

.. warning::

   

  Calling ``assume-role-with-saml`` can result in an entry in your AWS CloudTrail logs. The entry includes the value in the ``NameID`` element of the SAML assertion. We recommend that you use a NameIDType that is not associated with any personally identifiable information (PII). For example, you could instead use the Persistent Identifier (``urn:oasis:names:tc:SAML:2.0:nameid-format:persistent`` ).

   

 

For more information, see the following resources:

 

 
* `About SAML 2.0-based Federation <http://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_providers_saml.html>`_ in the *IAM User Guide* .  
 
* `Creating SAML Identity Providers <http://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_providers_create_saml.html>`_ in the *IAM User Guide* .  
 
* `Configuring a Relying Party and Claims <http://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_providers_create_saml_relying-party.html>`_ in the *IAM User Guide* .  
 
* `Creating a Role for SAML 2.0 Federation <http://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_create_for-idp_saml.html>`_ in the *IAM User Guide* .  
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sts-2011-06-15/AssumeRoleWithSAML>`_


========
Synopsis
========

::

    assume-role-with-saml
  --role-arn <value>
  --principal-arn <value>
  --saml-assertion <value>
  [--policy <value>]
  [--duration-seconds <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--role-arn`` (string)


  The Amazon Resource Name (ARN) of the role that the caller is assuming.

  

``--principal-arn`` (string)


  The Amazon Resource Name (ARN) of the SAML provider in IAM that describes the IdP.

  

``--saml-assertion`` (string)


  The base-64 encoded SAML authentication response provided by the IdP.

   

  For more information, see `Configuring a Relying Party and Adding Claims <http://docs.aws.amazon.com/IAM/latest/UserGuide/create-role-saml-IdP-tasks.html>`_ in the *Using IAM* guide. 

  

``--policy`` (string)


  An IAM policy in JSON format.

   

  The policy parameter is optional. If you pass a policy, the temporary security credentials that are returned by the operation have the permissions that are allowed by both the access policy of the role that is being assumed, * **and** * the policy that you pass. This gives you a way to further restrict the permissions for the resulting temporary security credentials. You cannot use the passed policy to grant permissions that are in excess of those allowed by the access policy of the role that is being assumed. For more information, `Permissions for AssumeRole, AssumeRoleWithSAML, and assume-role-with-web-identity <http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp_control-access_assumerole.html>`_ in the *IAM User Guide* . 

   

  The format for this parameter, as described by its regex pattern, is a string of characters up to 2048 characters in length. The characters can be any ASCII character from the space character to the end of the valid character list (\u0020-\u00FF). It can also include the tab (\u0009), linefeed (\u000A), and carriage return (\u000D) characters.

   

  .. note::

     

    The policy plain text must be 2048 bytes or shorter. However, an internal conversion compresses it into a packed binary format with a separate limit. The PackedPolicySize response element indicates by percentage how close to the upper size limit the policy is, with 100% equaling the maximum allowed size.

     

  

``--duration-seconds`` (integer)


  The duration, in seconds, of the role session. The value can range from 900 seconds (15 minutes) to 3600 seconds (1 hour). By default, the value is set to 3600 seconds. An expiration can also be specified in the SAML authentication response's ``SessionNotOnOrAfter`` value. The actual expiration time is whichever value is shorter. 

   

  .. note::

     

    This is separate from the duration of a console session that you might request using the returned credentials. The request to the federation endpoint for a console sign-in token takes a ``SessionDuration`` parameter that specifies the maximum length of the console session, separately from the ``DurationSeconds`` parameter on this API. For more information, see `Enabling SAML 2.0 Federated Users to Access the AWS Management Console <http://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_providers_enable-console-saml.html>`_ in the *IAM User Guide* .

     

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

  

  The identifiers for the temporary security credentials that the operation returns.

  

  AssumedRoleId -> (string)

    

    A unique identifier that contains the role ID and the role session name of the role that is being assumed. The role ID is generated by AWS when the role is created.

    

    

  Arn -> (string)

    

    The ARN of the temporary security credentials that are returned from the  assume-role action. For more information about ARNs and how to use them in policies, see `IAM Identifiers <http://docs.aws.amazon.com/IAM/latest/UserGuide/reference_identifiers.html>`_ in *Using IAM* . 

    

    

  

PackedPolicySize -> (integer)

  

  A percentage value that indicates the size of the policy in packed form. The service rejects any policy with a packed size greater than 100 percent, which means the policy exceeded the allowed space.

  

  

Subject -> (string)

  

  The value of the ``NameID`` element in the ``Subject`` element of the SAML assertion.

  

  

SubjectType -> (string)

  

  The format of the name ID, as defined by the ``Format`` attribute in the ``NameID`` element of the SAML assertion. Typical examples of the format are ``transient`` or ``persistent`` . 

   

  If the format includes the prefix ``urn:oasis:names:tc:SAML:2.0:nameid-format`` , that prefix is removed. For example, ``urn:oasis:names:tc:SAML:2.0:nameid-format:transient`` is returned as ``transient`` . If the format includes any other prefix, the format is returned with no modifications.

  

  

Issuer -> (string)

  

  The value of the ``Issuer`` element of the SAML assertion.

  

  

Audience -> (string)

  

  The value of the ``Recipient`` attribute of the ``SubjectConfirmationData`` element of the SAML assertion. 

  

  

NameQualifier -> (string)

  

  A hash value based on the concatenation of the ``Issuer`` response value, the AWS account ID, and the friendly name (the last part of the ARN) of the SAML provider in IAM. The combination of ``NameQualifier`` and ``Subject`` can be used to uniquely identify a federated user. 

   

  The following pseudocode shows how the hash value is calculated:

   

   ``BASE64 ( SHA1 ( "https://example.com/saml" + "123456789012" + "/MySAMLIdP" ) )``  

  

  

