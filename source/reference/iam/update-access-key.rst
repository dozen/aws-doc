[ :ref:`aws <cli:aws>` . :ref:`iam <cli:aws iam>` ]

.. _cli:aws iam update-access-key:


*****************
update-access-key
*****************



===========
Description
===========



Changes the status of the specified access key from Active to Inactive, or vice versa. This action can be used to disable a user's key as part of a key rotation work flow. 

 

If the ``UserName`` field is not specified, the UserName is determined implicitly based on the AWS access key ID used to sign the request. Because this action works for access keys under the AWS account, you can use this action to manage root credentials even if the AWS account has no associated users. 

 

For information about rotating keys, see `Managing Keys and Certificates`_ in the *IAM User Guide* . 



========
Synopsis
========

::

    update-access-key
  [--user-name <value>]
  --access-key-id <value>
  --status <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--user-name`` (string)


  The name of the user whose key you want to update.

  

``--access-key-id`` (string)


  The access key ID of the secret access key you want to update.

  

``--status`` (string)


  The status you want to assign to the secret access key. ``Active`` means the key can be used for API calls to AWS, while ``Inactive`` means the key cannot be used. 

  

  Possible values:

  
  *   ``Active``

  
  *   ``Inactive``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To activate or deactivate an access key for an IAM user**

The following ``update-access-key`` command deactivates the specified access key (access key ID and secret access key)
for the IAM user named ``Bob``::

  aws iam update-access-key --access-key-id AKIAIOSFODNN7EXAMPLE --status Inactive --user-name Bob

Deactivating the key means that it cannot be used for programmatic access to AWS. However, the key is still available and can be reactivated.

For more information, see `Creating, Modifying, and Viewing User Security Credentials`_ in the *Using IAM* guide.

.. _`Creating, Modifying, and Viewing User Security Credentials`: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_CreateAccessKey.html




======
Output
======

None

.. _Managing Keys and Certificates: http://docs.aws.amazon.com/IAM/latest/UserGuide/ManagingCredentials.html
