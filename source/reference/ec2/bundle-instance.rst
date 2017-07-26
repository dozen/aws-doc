[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 bundle-instance:


***************
bundle-instance
***************



===========
Description
===========



Bundles an Amazon instance store-backed Windows instance.

 

During bundling, only the root device volume (C:\) is bundled. Data on other instance store volumes is not preserved.

 

.. note::

   

  This action is not applicable for Linux/Unix instances or Windows instances that are backed by Amazon EBS.

   

 

For more information, see `Creating an Instance Store-Backed Windows AMI <http://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/Creating_InstanceStoreBacked_WinAMI.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/BundleInstance>`_


========
Synopsis
========

::

    bundle-instance
  --instance-id <value>
  [--storage <value>]
  [--dry-run | --no-dry-run]
  [--bucket <value>]
  [--prefix <value>]
  [--owner-akid <value>]
  [--owner-sak <value>]
  [--policy <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-id`` (string)


  The ID of the instance to bundle.

   

  Type: instance-id

   

  Default: None

   

  Required: Yes

  

``--storage`` (structure)


  The bucket in which to store the AMI. You can specify a bucket that you already own or a new bucket that Amazon EC2 creates on your behalf. If you specify a bucket that belongs to someone else, Amazon EC2 returns an error.

  



Shorthand Syntax::

    S3={AWSAccessKeyId=string,Bucket=string,Prefix=string,UploadPolicy=blob,UploadPolicySignature=string}




JSON Syntax::

  {
    "S3": {
      "AWSAccessKeyId": "string",
      "Bucket": "string",
      "Prefix": "string",
      "UploadPolicy": blob,
      "UploadPolicySignature": "string"
    }
  }



``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--bucket`` (string)
The bucket in which to store the AMI. You can specify a bucket that you already own or a new bucket that Amazon EC2 creates on your behalf. If you specify a bucket that belongs to someone else, Amazon EC2 returns an error.

``--prefix`` (string)
The prefix for the image component names being stored in Amazon S3.

``--owner-akid`` (string)
The access key ID of the owner of the Amazon S3 bucket.

``--owner-sak`` (string)
The AWS secret access key for the owner of the Amazon S3 bucket specified in the --bucket parameter. This parameter is required so that a signature can be computed for the policy.

``--policy`` (string)
An Amazon S3 upload policy that gives Amazon EC2 permission to upload items into Amazon S3 on the user's behalf. If you provide this parameter, you must also provide your secret access key, so we can create a policy signature for you (the secret access key is not passed to Amazon EC2). If you do not provide this parameter, we generate an upload policy for you automatically. For more information about upload policies see the sections about policy construction and signatures in the `Amazon Simple storage Service Developer Guide <http://docs.aws.amazon.com/AmazonS3/latest/dev/HTTPPOSTForms.html>`_ .

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To bundle an instance**

This example bundles instance ``i-1234567890abcdef0`` to a bucket called ``bundletasks``. Before you specify values for your access key IDs, review and follow the guidance in `Best Practices for Managing AWS Access Keys`_.

Command::

  aws ec2 bundle-instance --instance-id i-1234567890abcdef0 --bucket bundletasks --prefix winami --owner-akid AK12AJEXAMPLE --owner-sak example123example

Output::

  {
    "BundleTask": {
      "UpdateTime": "2015-09-15T13:30:35.000Z", 
      "InstanceId": "i-1234567890abcdef0", 
      "Storage": {
        "S3": {
          "Prefix": "winami", 
          "Bucket": "bundletasks"
        }
      }, 
      "State": "pending", 
      "StartTime": "2015-09-15T13:30:35.000Z", 
      "BundleId": "bun-294e041f"
    }
  }

.. _`Best Practices for Managing AWS Access Keys`: http://docs.aws.amazon.com/general/latest/gr/aws-access-keys-best-practices.html

======
Output
======

BundleTask -> (structure)

  

  Information about the bundle task.

  

  BundleId -> (string)

    

    The ID of the bundle task.

    

    

  BundleTaskError -> (structure)

    

    If the task fails, a description of the error.

    

    Code -> (string)

      

      The error code.

      

      

    Message -> (string)

      

      The error message.

      

      

    

  InstanceId -> (string)

    

    The ID of the instance associated with this bundle task.

    

    

  Progress -> (string)

    

    The level of task completion, as a percent (for example, 20%).

    

    

  StartTime -> (timestamp)

    

    The time this task started.

    

    

  State -> (string)

    

    The state of the task.

    

    

  Storage -> (structure)

    

    The Amazon S3 storage locations.

    

    S3 -> (structure)

      

      An Amazon S3 storage location.

      

      AWSAccessKeyId -> (string)

        

        The access key ID of the owner of the bucket. Before you specify a value for your access key ID, review and follow the guidance in `Best Practices for Managing AWS Access Keys <http://docs.aws.amazon.com/general/latest/gr/aws-access-keys-best-practices.html>`_ .

        

        

      Bucket -> (string)

        

        The bucket in which to store the AMI. You can specify a bucket that you already own or a new bucket that Amazon EC2 creates on your behalf. If you specify a bucket that belongs to someone else, Amazon EC2 returns an error.

        

        

      Prefix -> (string)

        

        The beginning of the file name of the AMI.

        

        

      UploadPolicy -> (blob)

        

        An Amazon S3 upload policy that gives Amazon EC2 permission to upload items into Amazon S3 on your behalf.

        

        

      UploadPolicySignature -> (string)

        

        The signature of the JSON document.

        

        

      

    

  UpdateTime -> (timestamp)

    

    The time of the most recent update for the task.

    

    

  

