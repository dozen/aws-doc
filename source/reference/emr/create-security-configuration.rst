[ :ref:`aws <cli:aws>` . :ref:`emr <cli:aws emr>` ]

.. _cli:aws emr create-security-configuration:


*****************************
create-security-configuration
*****************************



===========
Description
===========



Creates a security configuration, which is stored in the service and can be specified when a cluster is created.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticmapreduce-2009-03-31/CreateSecurityConfiguration>`_


========
Synopsis
========

::

    create-security-configuration
  --name <value>
  --security-configuration <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the security configuration.

  

``--security-configuration`` (string)


  The security configuration details in JSON format.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**1. To create a security configuration with in-transit encryption enabled with PEM for certificate provider, and at-rest encryption enabled with SSE-S3 for S3 encryption and AWS-KMS for local disk key provider**

- Command::

	 aws emr create-security-configuration --name MySecurityConfig --security-configuration '{
		"EncryptionConfiguration": {
			"EnableInTransitEncryption" : true,
			"EnableAtRestEncryption" : true,
			"InTransitEncryptionConfiguration" : {
				"TLSCertificateConfiguration" : {
					"CertificateProviderType" : "PEM",
					"S3Object" : "s3://mycertstore/artifacts/MyCerts.zip"
				}
			},
			"AtRestEncryptionConfiguration" : {
				"S3EncryptionConfiguration" : {
					"EncryptionMode" : "SSE-S3"
				},
				"LocalDiskEncryptionConfiguration" : {
					"EncryptionKeyProviderType" : "AwsKms",
					"AwsKmsKey" : "arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012"
				}
			}
		}
	}'

- Output::

    {
    "CreationDateTime": 1474070889.129,
    "Name": "MySecurityConfig"
    }

- JSON equivalent (contents of security_configuration.json)::

    {
        "EncryptionConfiguration": {
            "EnableInTransitEncryption": true,
            "EnableAtRestEncryption": true,
            "InTransitEncryptionConfiguration": {
                "TLSCertificateConfiguration": {
                    "CertificateProviderType": "PEM",
                    "S3Object": "s3://mycertstore/artifacts/MyCerts.zip"
                }
            },
            "AtRestEncryptionConfiguration": {
                "S3EncryptionConfiguration": {
                    "EncryptionMode": "SSE-S3"
                },
                "LocalDiskEncryptionConfiguration": {
                    "EncryptionKeyProviderType": "AwsKms",
                    "AwsKmsKey": "arn:aws:kms:us-east-1:123456789012:key/12345678-1234-1234-1234-123456789012"
                }
            }
        }
    }

- Command (using security_configuration.json)::

   aws emr create-security-configuration --name "MySecurityConfig" --security-configuration file://./security_configuration.json

- Output::

    {
    "CreationDateTime": 1474070889.129,
    "Name": "MySecurityConfig"
    }


======
Output
======

Name -> (string)

  

  The name of the security configuration.

  

  

CreationDateTime -> (timestamp)

  

  The date and time the security configuration was created.

  

  

