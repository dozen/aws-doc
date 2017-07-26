[ :ref:`aws <cli:aws>` . :ref:`sts <cli:aws sts>` ]

.. _cli:aws sts assume-role-with-web-identity:


*****************************
assume-role-with-web-identity
*****************************



===========
Description
===========



Returns a set of temporary security credentials for users who have been authenticated in a mobile or web application with a web identity provider, such as Amazon Cognito, Login with Amazon, Facebook, Google, or any OpenID Connect-compatible identity provider.

 

.. note::

   

  For mobile applications, we recommend that you use Amazon Cognito. You can use Amazon Cognito with the `AWS SDK for iOS <http://aws.amazon.com/sdkforios/>`_ and the `AWS SDK for Android <http://aws.amazon.com/sdkforandroid/>`_ to uniquely identify a user and supply the user with a consistent identity throughout the lifetime of an application.

   

  To learn more about Amazon Cognito, see `Amazon Cognito Overview <http://docs.aws.amazon.com/mobile/sdkforandroid/developerguide/cognito-auth.html#d0e840>`_ in the *AWS SDK for Android Developer Guide* guide and `Amazon Cognito Overview <http://docs.aws.amazon.com/mobile/sdkforios/developerguide/cognito-auth.html#d0e664>`_ in the *AWS SDK for iOS Developer Guide* .

   

 

Calling ``assume-role-with-web-identity`` does not require the use of AWS security credentials. Therefore, you can distribute an application (for example, on mobile devices) that requests temporary security credentials without including long-term AWS credentials in the application, and without deploying server-based proxy services that use long-term AWS credentials. Instead, the identity of the caller is validated by using a token from the web identity provider. For a comparison of ``assume-role-with-web-identity`` with the other APIs that produce temporary credentials, see `Requesting Temporary Security Credentials <http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp_request.html>`_ and `Comparing the AWS STS APIs <http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp_request.html#stsapi_comparison>`_ in the *IAM User Guide* .

 

The temporary security credentials returned by this API consist of an access key ID, a secret access key, and a security token. Applications can use these temporary security credentials to sign calls to AWS service APIs.

 

The credentials are valid for the duration that you specified when calling ``assume-role-with-web-identity`` , which can be from 900 seconds (15 minutes) to a maximum of 3600 seconds (1 hour). The default is 1 hour. 

 

The temporary security credentials created by ``assume-role-with-web-identity`` can be used to make API calls to any AWS service with the following exception: you cannot call the STS service's ``get-federation-token`` or ``get-session-token`` APIs.

 

Optionally, you can pass an IAM access policy to this operation. If you choose not to pass a policy, the temporary security credentials that are returned by the operation have the permissions that are defined in the access policy of the role that is being assumed. If you pass a policy to this operation, the temporary security credentials that are returned by the operation have the permissions that are allowed by both the access policy of the role that is being assumed, * **and** * the policy that you pass. This gives you a way to further restrict the permissions for the resulting temporary security credentials. You cannot use the passed policy to grant permissions that are in excess of those allowed by the access policy of the role that is being assumed. For more information, see `Permissions for AssumeRole, AssumeRoleWithSAML, and assume-role-with-web-identity <http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp_control-access_assumerole.html>`_ in the *IAM User Guide* .

 

Before your application can call ``assume-role-with-web-identity`` , you must have an identity token from a supported identity provider and create a role that the application can assume. The role that your application assumes must trust the identity provider that is associated with the identity token. In other words, the identity provider must be specified in the role's trust policy. 

 

.. warning::

   

  Calling ``assume-role-with-web-identity`` can result in an entry in your AWS CloudTrail logs. The entry includes the `Subject <http://openid.net/specs/openid-connect-core-1_0.html#Claims>`_ of the provided Web Identity Token. We recommend that you avoid using any personally identifiable information (PII) in this field. For example, you could instead use a GUID or a pairwise identifier, as `suggested in the OIDC specification <http://openid.net/specs/openid-connect-core-1_0.html#SubjectIDTypes>`_ .

   

 

For more information about how to use web identity federation and the ``assume-role-with-web-identity`` API, see the following resources: 

 

 
* `Using Web Identity Federation APIs for Mobile Apps <http://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_providers_oidc_manual.html>`_ and `Federation Through a Web-based Identity Provider <http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp_request.html#api_assumerolewithwebidentity>`_ .  
 
* `Web Identity Federation Playground <https://web-identity-federation-playground.s3.amazonaws.com/index.html>`_ . This interactive website lets you walk through the process of authenticating via Login with Amazon, Facebook, or Google, getting temporary security credentials, and then using those credentials to make a request to AWS.  
 
* `AWS SDK for iOS <http://aws.amazon.com/sdkforios/>`_ and `AWS SDK for Android <http://aws.amazon.com/sdkforandroid/>`_ . These toolkits contain sample apps that show how to invoke the identity providers, and then how to use the information from these providers to get and use temporary security credentials.  
 
* `Web Identity Federation with Mobile Applications <http://aws.amazon.com/articles/4617974389850313>`_ . This article discusses web identity federation and shows an example of how to use web identity federation to get access to content in Amazon S3.  
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/sts-2011-06-15/AssumeRoleWithWebIdentity>`_


========
Synopsis
========

::

    assume-role-with-web-identity
  --role-arn <value>
  --role-session-name <value>
  --web-identity-token <value>
  [--provider-id <value>]
  [--policy <value>]
  [--duration-seconds <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--role-arn`` (string)


  The Amazon Resource Name (ARN) of the role that the caller is assuming.

  

``--role-session-name`` (string)


  An identifier for the assumed role session. Typically, you pass the name or identifier that is associated with the user who is using your application. That way, the temporary security credentials that your application will use are associated with that user. This session name is included as part of the ARN and assumed role ID in the ``AssumedRoleUser`` response element.

   

  The regex used to validate this parameter is a string of characters consisting of upper- and lower-case alphanumeric characters with no spaces. You can also include underscores or any of the following characters: =,.@-

  

``--web-identity-token`` (string)


  The OAuth 2.0 access token or OpenID Connect ID token that is provided by the identity provider. Your application must get this token by authenticating the user who is using your application with a web identity provider before the application makes an ``assume-role-with-web-identity`` call. 

  

``--provider-id`` (string)


  The fully qualified host component of the domain name of the identity provider.

   

  Specify this value only for OAuth 2.0 access tokens. Currently ``www.amazon.com`` and ``graph.facebook.com`` are the only supported identity providers for OAuth 2.0 access tokens. Do not include URL schemes and port numbers.

   

  Do not specify this value for OpenID Connect ID tokens.

  

``--policy`` (string)


  An IAM policy in JSON format.

   

  The policy parameter is optional. If you pass a policy, the temporary security credentials that are returned by the operation have the permissions that are allowed by both the access policy of the role that is being assumed, * **and** * the policy that you pass. This gives you a way to further restrict the permissions for the resulting temporary security credentials. You cannot use the passed policy to grant permissions that are in excess of those allowed by the access policy of the role that is being assumed. For more information, see `Permissions for assume-role-with-web-identity <http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp_control-access_assumerole.html>`_ in the *IAM User Guide* . 

   

  The format for this parameter, as described by its regex pattern, is a string of characters up to 2048 characters in length. The characters can be any ASCII character from the space character to the end of the valid character list (\u0020-\u00FF). It can also include the tab (\u0009), linefeed (\u000A), and carriage return (\u000D) characters.

   

  .. note::

     

    The policy plain text must be 2048 bytes or shorter. However, an internal conversion compresses it into a packed binary format with a separate limit. The PackedPolicySize response element indicates by percentage how close to the upper size limit the policy is, with 100% equaling the maximum allowed size.

     

  

``--duration-seconds`` (integer)


  The duration, in seconds, of the role session. The value can range from 900 seconds (15 minutes) to 3600 seconds (1 hour). By default, the value is set to 3600 seconds.

   

  .. note::

     

    This is separate from the duration of a console session that you might request using the returned credentials. The request to the federation endpoint for a console sign-in token takes a ``SessionDuration`` parameter that specifies the maximum length of the console session, separately from the ``DurationSeconds`` parameter on this API. For more information, see `Creating a URL that Enables Federated Users to Access the AWS Management Console <http://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_providers_enable-console-custom-url.html>`_ in the *IAM User Guide* .

     

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Credentials -> (structure)

  

  The temporary security credentials, which include an access key ID, a secret access key, and a security token.

   

   **Note:** The size of the security token that STS APIs return is not fixed. We strongly recommend that you make no assumptions about the maximum size. As of this writing, the typical size is less than 4096 bytes, but that can vary. Also, future updates to AWS might require larger sizes.

  

  AccessKeyId -> (string)

    

    The access key ID that identifies the temporary security credentials.

    

    

  SecretAccessKey -> (string)

    

    The secret access key that can be used to sign requests.

    

    

  SessionToken -> (string)

    

    The token that users must pass to the service API to use the temporary credentials.

    

    

  Expiration -> (timestamp)

    

    The date on which the current credentials expire.

    

    

  

SubjectFromWebIdentityToken -> (string)

  

  The unique user identifier that is returned by the identity provider. This identifier is associated with the ``WebIdentityToken`` that was submitted with the ``assume-role-with-web-identity`` call. The identifier is typically unique to the user and the application that acquired the ``WebIdentityToken`` (pairwise identifier). For OpenID Connect ID tokens, this field contains the value returned by the identity provider as the token's ``sub`` (Subject) claim. 

  

  

AssumedRoleUser -> (structure)

  

  The Amazon Resource Name (ARN) and the assumed role ID, which are identifiers that you can use to refer to the resulting temporary security credentials. For example, you can reference these credentials as a principal in a resource-based policy by using the ARN or assumed role ID. The ARN and ID include the ``RoleSessionName`` that you specified when you called ``assume-role`` . 

  

  AssumedRoleId -> (string)

    

    A unique identifier that contains the role ID and the role session name of the role that is being assumed. The role ID is generated by AWS when the role is created.

    

    

  Arn -> (string)

    

    The ARN of the temporary security credentials that are returned from the  assume-role action. For more information about ARNs and how to use them in policies, see `IAM Identifiers <http://docs.aws.amazon.com/IAM/latest/UserGuide/reference_identifiers.html>`_ in *Using IAM* . 

    

    

  

PackedPolicySize -> (integer)

  

  A percentage value that indicates the size of the policy in packed form. The service rejects any policy with a packed size greater than 100 percent, which means the policy exceeded the allowed space.

  

  

Provider -> (string)

  

  The issuing authority of the web identity token presented. For OpenID Connect ID Tokens this contains the value of the ``iss`` field. For OAuth 2.0 access tokens, this contains the value of the ``ProviderId`` parameter that was passed in the ``assume-role-with-web-identity`` request.

  

  

Audience -> (string)

  

  The intended audience (also known as client ID) of the web identity token. This is traditionally the client identifier issued to the application that requested the web identity token.

  

  

