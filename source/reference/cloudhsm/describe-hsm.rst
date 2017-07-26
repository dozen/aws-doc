[ :ref:`aws <cli:aws>` . :ref:`cloudhsm <cli:aws cloudhsm>` ]

.. _cli:aws cloudhsm describe-hsm:


************
describe-hsm
************



===========
Description
===========



Retrieves information about an HSM. You can identify the HSM by its ARN or its serial number.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cloudhsm-2014-05-30/DescribeHsm>`_


========
Synopsis
========

::

    describe-hsm
  [--hsm-arn <value>]
  [--hsm-serial-number <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--hsm-arn`` (string)


  The ARN of the HSM. Either the *hsm-arn* or the *SerialNumber* parameter must be specified.

  

``--hsm-serial-number`` (string)


  The serial number of the HSM. Either the *hsm-arn* or the *hsm-serial-number* parameter must be specified.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

HsmArn -> (string)

  

  The ARN of the HSM.

  

  

Status -> (string)

  

  The status of the HSM.

  

  

StatusDetails -> (string)

  

  Contains additional information about the status of the HSM.

  

  

AvailabilityZone -> (string)

  

  The Availability Zone that the HSM is in.

  

  

EniId -> (string)

  

  The identifier of the elastic network interface (ENI) attached to the HSM.

  

  

EniIp -> (string)

  

  The IP address assigned to the HSM's ENI.

  

  

SubscriptionType -> (string)

  

  Specifies the type of subscription for the HSM.

   

   
  * **PRODUCTION** - The HSM is being used in a production environment.
   
  * **TRIAL** - The HSM is being used in a product trial.
   

  

  

SubscriptionStartDate -> (string)

  

  The subscription start date.

  

  

SubscriptionEndDate -> (string)

  

  The subscription end date.

  

  

VpcId -> (string)

  

  The identifier of the VPC that the HSM is in.

  

  

SubnetId -> (string)

  

  The identifier of the subnet that the HSM is in.

  

  

IamRoleArn -> (string)

  

  The ARN of the IAM role assigned to the HSM.

  

  

SerialNumber -> (string)

  

  The serial number of the HSM.

  

  

VendorName -> (string)

  

  The name of the HSM vendor.

  

  

HsmType -> (string)

  

  The HSM model type.

  

  

SoftwareVersion -> (string)

  

  The HSM software version.

  

  

SshPublicKey -> (string)

  

  The public SSH key.

  

  

SshKeyLastUpdated -> (string)

  

  The date and time that the SSH key was last updated.

  

  

ServerCertUri -> (string)

  

  The URI of the certificate server.

  

  

ServerCertLastUpdated -> (string)

  

  The date and time that the server certificate was last updated.

  

  

Partitions -> (list)

  

  The list of partitions on the HSM.

  

  (string)

    

    

  

