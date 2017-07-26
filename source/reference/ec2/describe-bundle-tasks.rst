[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-bundle-tasks:


*********************
describe-bundle-tasks
*********************



===========
Description
===========



Describes one or more of your bundling tasks.

 

.. note::

  

  Completed bundle tasks are listed for only a limited time. If your bundle task is no longer in the list, you can still register an AMI from it. Just use ``register-image`` with the Amazon S3 bucket name and image manifest name you provided to the bundle task.

  



========
Synopsis
========

::

    describe-bundle-tasks
  [--dry-run | --no-dry-run]
  [--bundle-ids <value>]
  [--filters <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--bundle-ids`` (list)


  One or more bundle task IDs.

   

  Default: Describes all your bundle tasks.

  



Syntax::

  "string" "string" ...



``--filters`` (list)


  One or more filters.

   

   
  * ``bundle-id`` - The ID of the bundle task. 
   
  * ``error-code`` - If the task failed, the error code returned. 
   
  * ``error-message`` - If the task failed, the error message returned. 
   
  * ``instance-id`` - The ID of the instance. 
   
  * ``progress`` - The level of task completion, as a percentage (for example, 20%). 
   
  * ``s3-bucket`` - The Amazon S3 bucket to store the AMI. 
   
  * ``s3-prefix`` - The beginning of the AMI name. 
   
  * ``start-time`` - The time the task started (for example, 2013-09-15T17:15:20.000Z). 
   
  * ``state`` - The state of the task (``pending`` | ``waiting-for-shutdown`` | ``bundling`` | ``storing`` | ``cancelling`` | ``complete`` | ``failed`` ). 
   
  * ``update-time`` - The time of the most recent update for the task. 
   

  



Shorthand Syntax::

    Name=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Values": ["string", ...]
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe your bundle tasks**

This example describes all of your bundle tasks.

Command::

  aws ec2 describe-bundle-tasks

Output::

  {
    "BundleTasks": [
      {
        "UpdateTime": "2015-09-15T13:26:54.000Z", 
        "InstanceId": "i-1a2b3c4d", 
        "Storage": {
          "S3": {
              "Prefix": "winami", 
              "Bucket": "bundletasks"
          }
        }, 
        "State": "bundling", 
        "StartTime": "2015-09-15T13:24:35.000Z", 
        "Progress": "3%", 
        "BundleId": "bun-2a4e041c"
      }
    ]
  }

======
Output
======

BundleTasks -> (list)

  

  Information about one or more bundle tasks.

  

  (structure)

    

    Describes a bundle task.

    

    InstanceId -> (string)

      

      The ID of the instance associated with this bundle task.

      

      

    BundleId -> (string)

      

      The ID of the bundle task.

      

      

    State -> (string)

      

      The state of the task.

      

      

    StartTime -> (timestamp)

      

      The time this task started.

      

      

    UpdateTime -> (timestamp)

      

      The time of the most recent update for the task.

      

      

    Storage -> (structure)

      

      The Amazon S3 storage locations.

      

      S3 -> (structure)

        

        An Amazon S3 storage location.

        

        Bucket -> (string)

          

          The bucket in which to store the AMI. You can specify a bucket that you already own or a new bucket that Amazon EC2 creates on your behalf. If you specify a bucket that belongs to someone else, Amazon EC2 returns an error.

          

          

        Prefix -> (string)

          

          The beginning of the file name of the AMI.

          

          

        AWSAccessKeyId -> (string)

          

          The access key ID of the owner of the bucket. Before you specify a value for your access key ID, review and follow the guidance in `Best Practices for Managing AWS Access Keys`_ .

          

          

        UploadPolicy -> (blob)

          

          A Base64-encoded Amazon S3 upload policy that gives Amazon EC2 permission to upload items into Amazon S3 on your behalf.

          

          

        UploadPolicySignature -> (string)

          

          The signature of the Base64 encoded JSON document.

          

          

        

      

    Progress -> (string)

      

      The level of task completion, as a percent (for example, 20%).

      

      

    BundleTaskError -> (structure)

      

      If the task fails, a description of the error.

      

      Code -> (string)

        

        The error code.

        

        

      Message -> (string)

        

        The error message.

        

        

      

    

  



.. _Best Practices for Managing AWS Access Keys: http://docs.aws.amazon.com/general/latest/gr/aws-access-keys-best-practices.html
