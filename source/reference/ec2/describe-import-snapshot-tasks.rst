[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-import-snapshot-tasks:


******************************
describe-import-snapshot-tasks
******************************



===========
Description
===========



Describes your import snapshot tasks.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeImportSnapshotTasks>`_


========
Synopsis
========

::

    describe-import-snapshot-tasks
  [--dry-run | --no-dry-run]
  [--filters <value>]
  [--import-task-ids <value>]
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




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



``--import-task-ids`` (list)


  A list of import snapshot task IDs.

  



Syntax::

  "string" "string" ...



``--max-results`` (integer)


  The maximum number of results to return in a single call. To retrieve the remaining results, make another call with the returned ``NextToken`` value.

  

``--next-token`` (string)


  A token that indicates the next page of results.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ImportSnapshotTasks -> (list)

  

  A list of zero or more import snapshot tasks that are currently active or were completed or canceled in the previous 7 days.

  

  (structure)

    

    Describes an import snapshot task.

    

    Description -> (string)

      

      A description of the import snapshot task.

      

      

    ImportTaskId -> (string)

      

      The ID of the import snapshot task.

      

      

    SnapshotTaskDetail -> (structure)

      

      Describes an import snapshot task.

      

      Description -> (string)

        

        The description of the snapshot.

        

        

      DiskImageSize -> (double)

        

        The size of the disk in the snapshot, in GiB.

        

        

      Format -> (string)

        

        The format of the disk image from which the snapshot is created.

        

        

      Progress -> (string)

        

        The percentage of completion for the import snapshot task.

        

        

      SnapshotId -> (string)

        

        The snapshot ID of the disk being imported.

        

        

      Status -> (string)

        

        A brief status for the import snapshot task.

        

        

      StatusMessage -> (string)

        

        A detailed status message for the import snapshot task.

        

        

      Url -> (string)

        

        The URL of the disk image from which the snapshot is created.

        

        

      UserBucket -> (structure)

        

        The S3 bucket for the disk image.

        

        S3Bucket -> (string)

          

          The S3 bucket from which the disk image was created.

          

          

        S3Key -> (string)

          

          The file name of the disk image.

          

          

        

      

    

  

NextToken -> (string)

  

  The token to use to get the next page of results. This value is ``null`` when there are no more results to return.

  

  

