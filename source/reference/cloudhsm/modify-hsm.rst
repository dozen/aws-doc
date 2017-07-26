[ :ref:`aws <cli:aws>` . :ref:`cloudhsm <cli:aws cloudhsm>` ]

.. _cli:aws cloudhsm modify-hsm:


**********
modify-hsm
**********



===========
Description
===========



Modifies an HSM.



========
Synopsis
========

::

    modify-hsm
  --hsm-arn <value>
  [--subnet-id <value>]
  [--eni-ip <value>]
  [--iam-role-arn <value>]
  [--external-id <value>]
  [--syslog-ip <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--hsm-arn`` (string)


  The ARN of the HSM to modify.

  

``--subnet-id`` (string)


  The new identifier of the subnet that the HSM is in.

  

``--eni-ip`` (string)


  The new IP address for the elastic network interface attached to the HSM.

  

``--iam-role-arn`` (string)


  The new IAM role ARN.

  

``--external-id`` (string)


  The new external ID.

  

``--syslog-ip`` (string)


  The new IP address for the syslog monitoring server.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

HsmArn -> (string)

  

  The ARN of the HSM.

  

  

