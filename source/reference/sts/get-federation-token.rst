[ :ref:`aws <cli:aws>` . :ref:`sts <cli:aws sts>` ]

.. _cli:aws sts get-federation-token:


********************
get-federation-token
********************



===========
Description
===========



Returns a set of temporary security credentials (consisting of an access key ID, a secret access key, and a security token) for a federated user. A typical use is in a proxy application that gets temporary security credentials on behalf of distributed applications inside a corporate network. Because you must call the ``get-federation-token`` action using the long-term security credentials of an IAM user, this call is appropriate in contexts where those credentials can be safely stored, usually in a server-based application.

 

.. note::

   

  If you are creating a mobile-based or browser-based app that can authenticate users using a web identity provider like Login with Amazon, Facebook, Google, or an OpenID Connect-compatible identity provider, we recommend that you use `Amazon Cognito`_ or ``assume-role-with-web-identity`` . For more information, see `Federation Through a Web-based Identity Provider`_ .

   

 

The ``get-federation-token`` action must be called by using the long-term AWS security credentials of an IAM user. You can also call ``get-federation-token`` using the security credentials of an AWS account (root), but this is not recommended. Instead, we recommend that you create an IAM user for the purpose of the proxy application and then attach a policy to the IAM user that limits federated users to only the actions and resources they need access to. For more information, see `IAM Best Practices`_ in the *Using IAM* . 

 

The temporary security credentials that are obtained by using the long-term credentials of an IAM user are valid for the specified duration, between 900 seconds (15 minutes) and 129600 seconds (36 hours). Temporary credentials that are obtained by using AWS account (root) credentials have a maximum duration of 3600 seconds (1 hour)

 

 **Permissions**  

 

The permissions for the temporary security credentials returned by ``get-federation-token`` are determined by a combination of the following: 

 

 
* The policy or policies that are attached to the IAM user whose credentials are used to call ``get-federation-token`` .
 
* The policy that is passed as a parameter in the call.
 

 

The passed policy is attached to the temporary security credentials that result from the ``get-federation-token`` API call--that is, to the *federated user* . When the federated user makes an AWS request, AWS evaluates the policy attached to the federated user in combination with the policy or policies attached to the IAM user whose credentials were used to call ``get-federation-token`` . AWS allows the federated user's request only when both the federated user ***and*** the IAM user are explicitly allowed to perform the requested action. The passed policy cannot grant more permissions than those that are defined in the IAM user policy.

 

A typical use case is that the permissions of the IAM user whose credentials are used to call ``get-federation-token`` are designed to allow access to all the actions and resources that any federated user will need. Then, for individual users, you pass a policy to the operation that scopes down the permissions to a level that's appropriate to that individual user, using a policy that allows only a subset of permissions that are granted to the IAM user. 

 

If you do not pass a policy, the resulting temporary security credentials have no effective permissions. The only exception is when the temporary security credentials are used to access a resource that has a resource-based policy that specifically allows the federated user to access the resource. 

 

For more information about how permissions work, see `Permissions for get-federation-token`_ . For information about using ``get-federation-token`` to create temporary security credentials, see `GetFederationToken—Federation Through a Custom Identity Broker`_ . 



========
Synopsis
========

::

    get-federation-token
  --name <value>
  [--policy <value>]
  [--duration-seconds <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--name`` (string)


  The name of the federated user. The name is used as an identifier for the temporary security credentials (such as ``Bob`` ). For example, you can reference the federated user name in a resource-based policy, such as in an Amazon S3 bucket policy. 

  

``--policy`` (string)


  An IAM policy in JSON format that is passed with the ``get-federation-token`` call and evaluated along with the policy or policies that are attached to the IAM user whose credentials are used to call ``get-federation-token`` . The passed policy is used to scope down the permissions that are available to the IAM user, by allowing only a subset of the permissions that are granted to the IAM user. The passed policy cannot grant more permissions than those granted to the IAM user. The final permissions for the federated user are the most restrictive set based on the intersection of the passed policy and the IAM user policy.

   

  If you do not pass a policy, the resulting temporary security credentials have no effective permissions. The only exception is when the temporary security credentials are used to access a resource that has a resource-based policy that specifically allows the federated user to access the resource. 

   

  .. note::

    The policy plain text must be 2048 bytes or shorter. However, an internal conversion compresses it into a packed binary format with a separate limit. The PackedPolicySize response element indicates by percentage how close to the upper size limit the policy is, with 100% equaling the maximum allowed size. 

   

  For more information about how permissions work, see `Permissions for get-federation-token`_ .

  

``--duration-seconds`` (integer)


  The duration, in seconds, that the session should last. Acceptable durations for federation sessions range from 900 seconds (15 minutes) to 129600 seconds (36 hours), with 43200 seconds (12 hours) as the default. Sessions obtained using AWS account (root) credentials are restricted to a maximum of 3600 seconds (one hour). If the specified duration is longer than one hour, the session obtained by using AWS account (root) credentials defaults to one hour. 

  

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

    

    

  

FederatedUser -> (structure)

  

  Identifiers for the federated user associated with the credentials (such as ``arn:aws:sts::123456789012:federated-user/Bob`` or ``123456789012:Bob`` ). You can use the federated user's ARN in your resource-based policies, such as an Amazon S3 bucket policy. 

  

  FederatedUserId -> (string)

    

    The string that identifies the federated user associated with the credentials, similar to the unique ID of an IAM user.

    

    

  Arn -> (string)

    

    The ARN that specifies the federated user that is associated with the credentials. For more information about ARNs and how to use them in policies, see `IAM Identifiers`_ in *Using IAM* . 

    

    

  

PackedPolicySize -> (integer)

  

  A percentage value indicating the size of the policy in packed form. The service rejects policies for which the packed size is greater than 100 percent of the allowed value. 

  

  



.. _Federation Through a Web-based Identity Provider: http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp_request.html#api_assumerolewithwebidentity
.. _IAM Identifiers: http://docs.aws.amazon.com/IAM/latest/UserGuide/reference_identifiers.html
.. _Permissions for get-federation-token: http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp_control-access_getfederationtoken.html
.. _IAM Best Practices: http://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html
.. _Amazon Cognito: http://aws.amazon.com/cognito/
.. _GetFederationToken—Federation Through a Custom Identity Broker: http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp_request.html#api_getfederationtoken
