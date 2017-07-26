[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 copy-image:


**********
copy-image
**********



===========
Description
===========



Initiates the copy of an AMI from the specified source region to the current region. You specify the destination region by using its endpoint when making the request.

 

For more information, see `Copying AMIs`_ in the *Amazon Elastic Compute Cloud User Guide* .



========
Synopsis
========

::

    copy-image
  [--dry-run | --no-dry-run]
  --source-region <value>
  --source-image-id <value>
  --name <value>
  [--description <value>]
  [--client-token <value>]
  [--encrypted | --no-encrypted]
  [--kms-key-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--source-region`` (string)


  The name of the region that contains the AMI to copy.

  

``--source-image-id`` (string)


  The ID of the AMI to copy.

  

``--name`` (string)


  The name of the new AMI in the destination region.

  

``--description`` (string)


  A description for the new AMI in the destination region.

  

``--client-token`` (string)


  Unique, case-sensitive identifier you provide to ensure idempotency of the request. For more information, see `How to Ensure Idempotency`_ in the *Amazon Elastic Compute Cloud User Guide* .

  

``--encrypted`` | ``--no-encrypted`` (boolean)


  Specifies whether the destination snapshots of the copied image should be encrypted. The default CMK for EBS is used unless a non-default AWS Key Management Service (AWS KMS) CMK is specified with ``KmsKeyId`` . For more information, see `Amazon EBS Encryption`_ in the *Amazon Elastic Compute Cloud User Guide* .

  

``--kms-key-id`` (string)


  The full ARN of the AWS Key Management Service (AWS KMS) CMK to use when encrypting the snapshots of an image during a copy operation. This parameter is only required if you want to use a non-default CMK; if this parameter is not specified, the default CMK for EBS is used. The ARN contains the ``arn:aws:kms`` namespace, followed by the region of the CMK, the AWS account ID of the CMK owner, the ``key`` namespace, and then the CMK ID. For example, arn:aws:kms:*us-east-1* :*012345678910* :key/*abcd1234-a123-456a-a12b-a123b4cd56ef* . The specified CMK must exist in the region that the snapshot is being copied to. If a ``KmsKeyId`` is specified, the ``Encrypted`` flag must also be set.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To copy an AMI to another region**

This example copies the specified AMI from the ``us-east-1`` region to the ``ap-northeast-1`` region.

Command::

  aws ec2 copy-image --source-image-id ami-5731123e --source-region us-east-1 --region ap-northeast-1 --name "My server"

Output::

  {
      "ImageId": "ami-438bea42"
  }

======
Output
======

ImageId -> (string)

  

  The ID of the new AMI.

  

  



.. _Copying AMIs: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/CopyingAMIs.html
.. _Amazon EBS Encryption: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSEncryption.html
.. _How to Ensure Idempotency: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Run_Instance_Idempotency.html
