[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-conversion-tasks:


*************************
describe-conversion-tasks
*************************



===========
Description
===========



Describes one or more of your conversion tasks. For more information, see the `VM Import/Export User Guide <http://docs.aws.amazon.com/vm-import/latest/userguide/>`_ .

 

For information about the import manifest referenced by this API action, see `VM Import Manifest <http://docs.aws.amazon.com/AWSEC2/latest/APIReference/manifest.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeConversionTasks>`_


========
Synopsis
========

::

    describe-conversion-tasks
  [--conversion-task-ids <value>]
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--conversion-task-ids`` (list)


  One or more conversion task IDs.

  



Syntax::

  "string" "string" ...



``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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
                  "InstanceId": "i-1234567890abcdef0",
                  "Volumes": [
                      {
                          "Volume": {
                              "Id": "vol-049df61146c4d7901",
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

      

      Description -> (string)

        

        A description of the task.

        

        

      InstanceId -> (string)

        

        The ID of the instance.

        

        

      Platform -> (string)

        

        The instance operating system.

        

        

      Volumes -> (list)

        

        One or more volumes.

        

        (structure)

          

          Describes an import volume task.

          

          AvailabilityZone -> (string)

            

            The Availability Zone where the resulting instance will reside.

            

            

          BytesConverted -> (long)

            

            The number of bytes converted so far.

            

            

          Description -> (string)

            

            A description of the task.

            

            

          Image -> (structure)

            

            The image.

            

            Checksum -> (string)

              

              The checksum computed for the disk image.

              

              

            Format -> (string)

              

              The disk image format.

              

              

            ImportManifestUrl -> (string)

              

              A presigned URL for the import manifest stored in Amazon S3. For information about creating a presigned URL for an Amazon S3 object, read the "Query String Request Authentication Alternative" section of the `Authenticating REST Requests <http://docs.aws.amazon.com/AmazonS3/latest/dev/RESTAuthentication.html>`_ topic in the *Amazon Simple Storage Service Developer Guide* .

               

              For information about the import manifest referenced by this API action, see `VM Import Manifest <http://docs.aws.amazon.com/AWSEC2/latest/APIReference/manifest.html>`_ .

              

              

            Size -> (long)

              

              The size of the disk image, in GiB.

              

              

            

          Status -> (string)

            

            The status of the import of this particular disk image.

            

            

          StatusMessage -> (string)

            

            The status information or errors related to the disk image.

            

            

          Volume -> (structure)

            

            The volume.

            

            Id -> (string)

              

              The volume identifier.

              

              

            Size -> (long)

              

              The size of the volume, in GiB.

              

              

            

          

        

      

    ImportVolume -> (structure)

      

      If the task is for importing a volume, this contains information about the import volume task.

      

      AvailabilityZone -> (string)

        

        The Availability Zone where the resulting volume will reside.

        

        

      BytesConverted -> (long)

        

        The number of bytes converted so far.

        

        

      Description -> (string)

        

        The description you provided when starting the import volume task.

        

        

      Image -> (structure)

        

        The image.

        

        Checksum -> (string)

          

          The checksum computed for the disk image.

          

          

        Format -> (string)

          

          The disk image format.

          

          

        ImportManifestUrl -> (string)

          

          A presigned URL for the import manifest stored in Amazon S3. For information about creating a presigned URL for an Amazon S3 object, read the "Query String Request Authentication Alternative" section of the `Authenticating REST Requests <http://docs.aws.amazon.com/AmazonS3/latest/dev/RESTAuthentication.html>`_ topic in the *Amazon Simple Storage Service Developer Guide* .

           

          For information about the import manifest referenced by this API action, see `VM Import Manifest <http://docs.aws.amazon.com/AWSEC2/latest/APIReference/manifest.html>`_ .

          

          

        Size -> (long)

          

          The size of the disk image, in GiB.

          

          

        

      Volume -> (structure)

        

        The volume.

        

        Id -> (string)

          

          The volume identifier.

          

          

        Size -> (long)

          

          The size of the volume, in GiB.

          

          

        

      

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

          

          

        

      

    

  

