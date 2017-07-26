[ :ref:`aws <cli:aws>` . :ref:`cloudhsm <cli:aws cloudhsm>` ]

.. _cli:aws cloudhsm create-hsm:


**********
create-hsm
**********



===========
Description
===========



Creates an uninitialized HSM instance. Running this command provisions an HSM appliance and will result in charges to your AWS account for the HSM.



========
Synopsis
========

::

    create-hsm
  --subnet-id <value>
  --ssh-key <value>
  [--eni-ip <value>]
  --iam-role-arn <value>
  [--external-id <value>]
  --subscription-type <value>
  [--client-token <value>]
  [--syslog-ip <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--subnet-id`` (string)


  The identifier of the subnet in your VPC in which to place the HSM.

  

``--ssh-key`` (string)


  The SSH public key to install on the HSM.

  

``--eni-ip`` (string)


  The IP address to assign to the HSM's ENI.

  

``--iam-role-arn`` (string)


  The ARN of an IAM role to enable the AWS CloudHSM service to allocate an ENI on your behalf.

  

``--external-id`` (string)


  The external ID from **iam-role-arn** , if present.

  

``--subscription-type`` (string)


  The subscription type.

  

  Possible values:

  
  *   ``PRODUCTION``

  

  

``--client-token`` (string)


  A user-defined token to ensure idempotence. Subsequent calls to this action with the same token will be ignored.

  

``--syslog-ip`` (string)


  The IP address for the syslog monitoring server.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

HsmArn -> (string)

  

  The ARN of the HSM.

  

  

