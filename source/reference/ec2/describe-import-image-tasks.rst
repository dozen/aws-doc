[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-import-image-tasks:


***************************
describe-import-image-tasks
***************************



===========
Description
===========



Displays details about an import virtual machine or import snapshot tasks that are already created.



========
Synopsis
========

::

    describe-import-image-tasks
  [--dry-run | --no-dry-run]
  [--import-task-ids <value>]
  [--next-token <value>]
  [--max-results <value>]
  [--filters <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--import-task-ids`` (list)


  A list of import image task IDs.

  



Syntax::

  "string" "string" ...



``--next-token`` (string)


  A token that indicates the next page of results.

  

``--max-results`` (integer)


  The maximum number of results to return in a single request.

  

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



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

ImportImageTasks -> (list)

  

  A list of zero or more import image tasks that are currently active or were completed or canceled in the previous 7 days.

  

  (structure)

    

    Describes an import image task.

    

    ImportTaskId -> (string)

      

      The ID of the import image task.

      

      

    Architecture -> (string)

      

      The architecture of the virtual machine.

       

      Valid values: ``i386`` | ``x86_64`` 

      

      

    LicenseType -> (string)

      

      The license type of the virtual machine.

      

      

    Platform -> (string)

      

      The description string for the import image task.

      

      

    Hypervisor -> (string)

      

      The target hypervisor for the import task.

       

      Valid values: ``xen`` 

      

      

    Description -> (string)

      

      A description of the import task.

      

      

    SnapshotDetails -> (list)

      

      Information about the snapshots.

      

      (structure)

        

        Describes the snapshot created from the imported disk.

        

        DiskImageSize -> (double)

          

          The size of the disk in the snapshot, in GiB.

          

          

        Description -> (string)

          

          A description for the snapshot.

          

          

        Format -> (string)

          

          The format of the disk image from which the snapshot is created.

          

          

        Url -> (string)

          

          The URL used to access the disk image.

          

          

        UserBucket -> (structure)

          

          Describes the S3 bucket for the disk image.

          

          S3Bucket -> (string)

            

            The S3 bucket from which the disk image was created.

            

            

          S3Key -> (string)

            

            The key from which the disk image was created.

            

            

          

        DeviceName -> (string)

          

          The block device mapping for the snapshot.

          

          

        SnapshotId -> (string)

          

          The snapshot ID of the disk being imported.

          

          

        Progress -> (string)

          

          The percentage of progress for the task.

          

          

        StatusMessage -> (string)

          

          A detailed status message for the snapshot creation.

          

          

        Status -> (string)

          

          A brief status of the snapshot creation.

          

          

        

      

    ImageId -> (string)

      

      The ID of the Amazon Machine Image (AMI) of the imported virtual machine.

      

      

    Progress -> (string)

      

      The percentage of progress of the import image task.

      

      

    StatusMessage -> (string)

      

      A descriptive status message for the import image task.

      

      

    Status -> (string)

      

      A brief status for the import image task.

      

      

    

  

NextToken -> (string)

  

  The token to use to get the next page of results. This value is ``null`` when there are no more results to return.

  

  

