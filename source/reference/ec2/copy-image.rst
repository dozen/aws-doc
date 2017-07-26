[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 copy-image:


**********
copy-image
**********



===========
Description
===========



Initiates the copy of an AMI from the specified source region to the current region. You specify the destination region by using its endpoint when making the request.

 

For more information about the prerequisites and limits when copying an AMI, see `Copying an AMI <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/CopyingAMIs.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/CopyImage>`_


========
Synopsis
========

::

    copy-image
  [--client-token <value>]
  [--description <value>]
  [--encrypted | --no-encrypted]
  [--kms-key-id <value>]
  --name <value>
  --source-image-id <value>
  --source-region <value>
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--client-token`` (string)


  Unique, case-sensitive identifier you provide to ensure idempotency of the request. For more information, see `How to Ensure Idempotency <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Run_Instance_Idempotency.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .

  

``--description`` (string)


  A description for the new AMI in the destination region.

  

``--encrypted`` | ``--no-encrypted`` (boolean)


  Specifies whether the destination snapshots of the copied image should be encrypted. The default CMK for EBS is used unless a non-default AWS Key Management Service (AWS KMS) CMK is specified with ``KmsKeyId`` . For more information, see `Amazon EBS Encryption <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSEncryption.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .

  

``--kms-key-id`` (string)


  The full ARN of the AWS Key Management Service (AWS KMS) CMK to use when encrypting the snapshots of an image during a copy operation. This parameter is only required if you want to use a non-default CMK; if this parameter is not specified, the default CMK for EBS is used. The ARN contains the ``arn:aws:kms`` namespace, followed by the region of the CMK, the AWS account ID of the CMK owner, the ``key`` namespace, and then the CMK ID. For example, arn:aws:kms:*us-east-1* :*012345678910* :key/*abcd1234-a123-456a-a12b-a123b4cd56ef* . The specified CMK must exist in the region that the snapshot is being copied to. If a ``KmsKeyId`` is specified, the ``Encrypted`` flag must also be set.

  

``--name`` (string)


  The name of the new AMI in the destination region.

  

``--source-image-id`` (string)


  The ID of the AMI to copy.

  

``--source-region`` (string)


  The name of the region that contains the AMI to copy.

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

  

  

