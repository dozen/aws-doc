[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 cancel-bundle-task:


******************
cancel-bundle-task
******************



===========
Description
===========



Cancels a bundling operation for an instance store-backed Windows instance.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/CancelBundleTask>`_


========
Synopsis
========

::

    cancel-bundle-task
  --bundle-id <value>
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--bundle-id`` (string)


  The ID of the bundle task.

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To cancel a bundle task**

This example cancels bundle task ``bun-2a4e041c``.

Command::

  aws ec2 cancel-bundle-task --bundle-id bun-2a4e041c

Output::

  {
    "BundleTask": {
      "UpdateTime": "2015-09-15T13:27:40.000Z", 
      "InstanceId": "i-1234567890abcdef0", 
      "Storage": {
        "S3": {
          "Prefix": "winami", 
          "Bucket": "bundletasks"
        }
      }, 
      "State": "cancelling", 
      "StartTime": "2015-09-15T13:24:35.000Z", 
      "BundleId": "bun-2a4e041c"
    }
  }

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

    

    

  

