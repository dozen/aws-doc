[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-conversion-tasks:


*************************
describe-conversion-tasks
*************************



===========
Description
===========



Describes one or more of your conversion tasks. For more information, see `Using the Command Line Tools to Import Your Virtual Machine to Amazon EC2`_ in the *Amazon Elastic Compute Cloud User Guide* .



========
Synopsis
========

::

    describe-conversion-tasks
  [--dry-run | --no-dry-run]
  [--filters <value>]
  [--conversion-task-ids <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--filters`` (list)


  One or more filters.

  



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



``--conversion-task-ids`` (list)


  One or more conversion task IDs.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To view the status of a conversion task**

This example returns the status of a conversion task with the ID import-i-ffvko9js.

Command::

  aws ec2 describe-conversion-tasks --conversion-task-ids import-i-ffvko9js

Output::

  {
      "ConversionTasks": [
          {
              "ConversionTaskId": "import-i-ffvko9js",
              "ImportInstance": {
                  "InstanceId": "i-6cc70a3f",
                  "Volumes": [
                      {
                          "Volume": {
                              "Id": "vol-99e2ebdb",
                              "Size": 16
                          },
                          "Status": "completed",
                          "Image": {
                              "Size": 1300687360,
                              "ImportManifestUrl": "https://s3.amazonaws.com/myimportbucket/411443cd-d620-4f1c-9d66-13144EXAMPLE/RHEL5.vmdkmanifest.xml?AWSAccessKeyId=AKIAIOSFODNN7EXAMPLE&Expires=140EXAMPLE&Signature=XYNhznHNgCqsjDxL9wRL%2FJvEXAMPLE",
                              "Format": "VMDK"
                          },
                          "BytesConverted": 1300682960,
                          "AvailabilityZone": "us-east-1d"
                      }
                  ]
              },
              "ExpirationTime": "2014-05-14T22:06:23Z",
              "State": "completed"
          }
      ]
  }


======
Output
======

ConversionTasks -> (list)

  

  Information about the conversion tasks.

  

  (structure)

    

    Describes a conversion task.

    

    ConversionTaskId -> (string)

      

      The ID of the conversion task.

      

      

    ExpirationTime -> (string)

      

      The time when the task expires. If the upload isn't complete before the expiration time, we automatically cancel the task.

      

      

    ImportInstance -> (structure)

      

      If the task is for importing an instance, this contains information about the import instance task.

      

      Volumes -> (list)

        

        One or more volumes.

        

        (structure)

          

          Describes an import volume task.

          

          BytesConverted -> (long)

            

            The number of bytes converted so far.

            

            

          AvailabilityZone -> (string)

            

            The Availability Zone where the resulting instance will reside.

            

            

          Image -> (structure)

            

            The image.

            

            Format -> (string)

              

              The disk image format.

              

              

            Size -> (long)

              

              The size of the disk image, in GiB.

              

              

            ImportManifestUrl -> (string)

              

              A presigned URL for the import manifest stored in Amazon S3. For information about creating a presigned URL for an Amazon S3 object, read the "Query String Request Authentication Alternative" section of the `Authenticating REST Requests`_ topic in the *Amazon Simple Storage Service Developer Guide* .

              

              

            Checksum -> (string)

              

              The checksum computed for the disk image.

              

              

            

          Volume -> (structure)

            

            The volume.

            

            Size -> (long)

              

              The size of the volume, in GiB.

              

              

            Id -> (string)

              

              The volume identifier.

              

              

            

          Status -> (string)

            

            The status of the import of this particular disk image.

            

            

          StatusMessage -> (string)

            

            The status information or errors related to the disk image.

            

            

          Description -> (string)

            

            A description of the task.

            

            

          

        

      InstanceId -> (string)

        

        The ID of the instance.

        

        

      Platform -> (string)

        

        The instance operating system.

        

        

      Description -> (string)

        

        A description of the task.

        

        

      

    ImportVolume -> (structure)

      

      If the task is for importing a volume, this contains information about the import volume task.

      

      BytesConverted -> (long)

        

        The number of bytes converted so far.

        

        

      AvailabilityZone -> (string)

        

        The Availability Zone where the resulting volume will reside.

        

        

      Description -> (string)

        

        The description you provided when starting the import volume task.

        

        

      Image -> (structure)

        

        The image.

        

        Format -> (string)

          

          The disk image format.

          

          

        Size -> (long)

          

          The size of the disk image, in GiB.

          

          

        ImportManifestUrl -> (string)

          

          A presigned URL for the import manifest stored in Amazon S3. For information about creating a presigned URL for an Amazon S3 object, read the "Query String Request Authentication Alternative" section of the `Authenticating REST Requests`_ topic in the *Amazon Simple Storage Service Developer Guide* .

          

          

        Checksum -> (string)

          

          The checksum computed for the disk image.

          

          

        

      Volume -> (structure)

        

        The volume.

        

        Size -> (long)

          

          The size of the volume, in GiB.

          

          

        Id -> (string)

          

          The volume identifier.

          

          

        

      

    State -> (string)

      

      The state of the conversion task.

      

      

    StatusMessage -> (string)

      

      The status message related to the conversion task.

      

      

    Tags -> (list)

      

      Any tags assigned to the task.

      

      (structure)

        

        Describes a tag.

        

        Key -> (string)

          

          The key of the tag. 

           

          Constraints: Tag keys are case-sensitive and accept a maximum of 127 Unicode characters. May not begin with ``aws:`` 

          

          

        Value -> (string)

          

          The value of the tag.

           

          Constraints: Tag values are case-sensitive and accept a maximum of 255 Unicode characters.

          

          

        

      

    

  



.. _Using the Command Line Tools to Import Your Virtual Machine to Amazon EC2: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/UploadingYourInstancesandVolumes.html
.. _Authenticating REST Requests: http://docs.aws.amazon.com/AmazonS3/latest/dev/RESTAuthentication.html
