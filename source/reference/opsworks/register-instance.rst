[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks register-instance:


*****************
register-instance
*****************



===========
Description
===========



Registers instances with a specified stack that were created outside of AWS OpsWorks.

 

.. note::

  We do not recommend using this action to register instances. The complete registration operation has two primary steps, installing the AWS OpsWorks agent on the instance and registering the instance with the stack. ``register-instance`` handles only the second step. You should instead use the AWS CLI ``register`` command, which performs the entire registration operation. For more information, see `Registering an Instance with an AWS OpsWorks Stack`_ .

 

**Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    register-instance
  --stack-id <value>
  [--hostname <value>]
  [--public-ip <value>]
  [--private-ip <value>]
  [--rsa-public-key <value>]
  [--rsa-public-key-fingerprint <value>]
  [--instance-identity <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--stack-id`` (string)


  The ID of the stack that the instance is to be registered with.

  

``--hostname`` (string)


  The instance's hostname.

  

``--public-ip`` (string)


  The instance's public IP address.

  

``--private-ip`` (string)


  The instance's private IP address.

  

``--rsa-public-key`` (string)


  The instances public RSA key. This key is used to encrypt communication between the instance and the service.

  

``--rsa-public-key-fingerprint`` (string)


  The instances public RSA key fingerprint.

  

``--instance-identity`` (structure)


  An instance-identity object that contains the instance's identity.

  



Shorthand Syntax::

    Document=string,Signature=string




JSON Syntax::

  {
    "Document": "string",
    "Signature": "string"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

InstanceId -> (string)

  

  The registered instance's AWS OpsWorks ID.

  

  



.. _Registering an Instance with an AWS OpsWorks Stack: http://docs.aws.amazon.com/opsworks/latest/userguide/registered-instances-register.html
.. _Managing User Permissions: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html
