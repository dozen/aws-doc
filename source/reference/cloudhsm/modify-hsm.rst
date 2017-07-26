[ :ref:`aws <cli:aws>` . :ref:`cloudhsm <cli:aws cloudhsm>` ]

.. _cli:aws cloudhsm modify-hsm:


**********
modify-hsm
**********



===========
Description
===========



Modifies an HSM.

 

.. warning::

   

  This operation can result in the HSM being offline for up to 15 minutes while the AWS CloudHSM service is reconfigured. If you are modifying a production HSM, you should ensure that your AWS CloudHSM service is configured for high availability, and consider executing this operation during a maintenance window.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudhsm-2014-05-30/ModifyHsm>`_


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
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--hsm-arn`` (string)


  The ARN of the HSM to modify.

  

``--subnet-id`` (string)


  The new identifier of the subnet that the HSM is in. The new subnet must be in the same Availability Zone as the current subnet.

  

``--eni-ip`` (string)


  The new IP address for the elastic network interface (ENI) attached to the HSM.

   

  If the HSM is moved to a different subnet, and an IP address is not specified, an IP address will be randomly chosen from the CIDR range of the new subnet.

  

``--iam-role-arn`` (string)


  The new IAM role ARN.

  

``--external-id`` (string)


  The new external ID.

  

``--syslog-ip`` (string)


  The new IP address for the syslog monitoring server. The AWS CloudHSM service only supports one syslog monitoring server.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

HsmArn -> (string)

  

  The ARN of the HSM.

  

  

