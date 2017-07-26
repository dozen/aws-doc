[ :ref:`aws <cli:aws>` . :ref:`cloudhsm <cli:aws cloudhsm>` ]

.. _cli:aws cloudhsm create-hsm:


**********
create-hsm
**********



===========
Description
===========



Creates an uninitialized HSM instance.

 

There is an upfront fee charged for each HSM instance that you create with the  create-hsm operation. If you accidentally provision an HSM and want to request a refund, delete the instance using the  delete-hsm operation, go to the `AWS Support Center <https://console.aws.amazon.com/support/home#/>`_ , create a new case, and select **Account and Billing Support** .

 

.. warning::

   

  It can take up to 20 minutes to create and provision an HSM. You can monitor the status of the HSM with the  describe-hsm operation. The HSM is ready to be initialized when the status changes to ``RUNNING`` .

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudhsm-2014-05-30/CreateHsm>`_


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
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--subnet-id`` (string)


  The identifier of the subnet in your VPC in which to place the HSM.

  

``--ssh-key`` (string)


  The SSH public key to install on the HSM.

  

``--eni-ip`` (string)


  The IP address to assign to the HSM's ENI.

   

  If an IP address is not specified, an IP address will be randomly chosen from the CIDR range of the subnet.

  

``--iam-role-arn`` (string)


  The ARN of an IAM role to enable the AWS CloudHSM service to allocate an ENI on your behalf.

  

``--external-id`` (string)


  The external ID from **iam-role-arn** , if present.

  

``--subscription-type`` (string)


  Specifies the type of subscription for the HSM.

   

   
  * **PRODUCTION** - The HSM is being used in a production environment.
   
  * **TRIAL** - The HSM is being used in a product trial.
   

  

  Possible values:

  
  *   ``PRODUCTION``

  

  

``--client-token`` (string)


  A user-defined token to ensure idempotence. Subsequent calls to this operation with the same token will be ignored.

  

``--syslog-ip`` (string)


  The IP address for the syslog monitoring server. The AWS CloudHSM service only supports one syslog monitoring server.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

HsmArn -> (string)

  

  The ARN of the HSM.

  

  

