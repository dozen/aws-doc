[ :ref:`aws <cli:aws>` . :ref:`sts <cli:aws sts>` ]

.. _cli:aws sts get-session-token:


*****************
get-session-token
*****************



===========
Description
===========



Returns a set of temporary credentials for an AWS account or IAM user. The credentials consist of an access key ID, a secret access key, and a security token. Typically, you use ``get-session-token`` if you want to use MFA to protect programmatic calls to specific AWS APIs like Amazon EC2 ``StopInstances`` . MFA-enabled IAM users would need to call ``get-session-token`` and submit an MFA code that is associated with their MFA device. Using the temporary security credentials that are returned from the call, IAM users can then make programmatic calls to APIs that require MFA authentication. If you do not supply a correct MFA code, then the API returns an access denied error.

 

The ``get-session-token`` action must be called by using the long-term AWS security credentials of the AWS account or an IAM user. Credentials that are created by IAM users are valid for the duration that you specify, between 900 seconds (15 minutes) and 129600 seconds (36 hours); credentials that are created by using account credentials have a maximum duration of 3600 seconds (1 hour). 

 

.. note::

   

  We recommend that you do not call ``get-session-token`` with root account credentials. Instead, follow our `best practices`_ by creating one or more IAM users, giving them the necessary permissions, and using IAM users for everyday interaction with AWS. 

   

 

The permissions associated with the temporary security credentials returned by ``get-session-token`` are based on the permissions associated with account or IAM user whose credentials are used to call the action. If ``get-session-token`` is called using root account credentials, the temporary credentials have root account permissions. Similarly, if ``get-session-token`` is called using the credentials of an IAM user, the temporary credentials have the same permissions as the IAM user. 

 

For more information about using ``get-session-token`` to create temporary credentials, go to `Temporary Credentials for Users in Untrusted Environments`_ in the *Using IAM* . 



========
Synopsis
========

::

    get-session-token
  [--duration-seconds <value>]
  [--serial-number <value>]
  [--token-code <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--duration-seconds`` (integer)


  The duration, in seconds, that the credentials should remain valid. Acceptable durations for IAM user sessions range from 900 seconds (15 minutes) to 129600 seconds (36 hours), with 43200 seconds (12 hours) as the default. Sessions for AWS account owners are restricted to a maximum of 3600 seconds (one hour). If the duration is longer than one hour, the session for AWS account owners defaults to one hour. 

  

``--serial-number`` (string)


  The identification number of the MFA device that is associated with the IAM user who is making the ``get-session-token`` call. Specify this value if the IAM user has a policy that requires MFA authentication. The value is either the serial number for a hardware device (such as ``GAHT12345678`` ) or an Amazon Resource Name (ARN) for a virtual device (such as ``arn:aws:iam::123456789012:mfa/user`` ). You can find the device for an IAM user by going to the AWS Management Console and viewing the user's security credentials. 

  

``--token-code`` (string)


  The value provided by the MFA device, if MFA is required. If any policy requires the IAM user to submit an MFA code, specify this value. If MFA authentication is required, and the user does not provide a code when requesting a set of temporary security credentials, the user will receive an "access denied" response when requesting resources that require MFA authentication.

  

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

    

    

  



.. _Temporary Credentials for Users in Untrusted Environments: http://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_temp_request.html#api_getsessiontoken
.. _best practices: http://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html#create-iam-users
