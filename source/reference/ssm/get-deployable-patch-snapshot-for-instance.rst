[ :ref:`aws <cli:aws>` . :ref:`ssm <cli:aws ssm>` ]

.. _cli:aws ssm get-deployable-patch-snapshot-for-instance:


******************************************
get-deployable-patch-snapshot-for-instance
******************************************



===========
Description
===========



Retrieves the current snapshot for the patch baseline the instance uses. This API is primarily used by the AWS-RunPatchBaseline Systems Manager document. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ssm-2014-11-06/GetDeployablePatchSnapshotForInstance>`_


========
Synopsis
========

::

    get-deployable-patch-snapshot-for-instance
  --instance-id <value>
  --snapshot-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-id`` (string)


  The ID of the instance for which the appropriate patch snapshot should be retrieved.

  

``--snapshot-id`` (string)


  The user-defined snapshot ID.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To retrieve the current snapshot for the patch baseline an instance uses**

This example displays the current snapshot for the patch baseline used by an Instance. This command must be run from the instance using the instance credentials. To ensure it uses the instance credentials, run ``aws configure`` and only specify the region of your instance but leave the ``Access Key`` and ``Secret Key`` fields blank.

Use ``uuidgen`` to generate a ``snapshot-id``.

Command::

  aws ssm get-deployable-patch-snapshot-for-instance --instance-id "i-0cb2b964d3e14fd9f" --snapshot-id "4681775b-098f-4435-a956-0ef33373ac11"

Output::

  {
    "InstanceId": "i-0cb2b964d3e14fd9f",
    "SnapshotId": "4681775b-098f-4435-a956-0ef33373ac11",
    "SnapshotDownloadUrl": "https://patch-baseline-snapshot-us-west-2.s3-us-west-2.amazonaws.com/853d0d3db0f0cafea3699f25b1c7ff101a13e25c3d05e832f613b0d2f79da62f-809632081692/4681775b-098f-4435-a956-0ef33373ac11?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Date=20170224T181926Z&X-Amz-SignedHeaders=host&X-Amz-Expires=86400&X-Amz-Credential=AKIAJI6YDVV7XJKZL7ZA%2F20170224%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Signature=2747799c958ffebf6f44bd698fd2071ccf9a303465febfab71ff29b46631a2d3"
  }


======
Output
======

InstanceId -> (string)

  

  The ID of the instance.

  

  

SnapshotId -> (string)

  

  The user-defined snapshot ID.

  

  

SnapshotDownloadUrl -> (string)

  

  A pre-signed Amazon S3 URL that can be used to download the patch snapshot.

  

  

Product -> (string)

  

  Returns the specific operating system (for example Windows Server 2012 or Amazon Linux 2015.09) on the instance for the specified patch snapshot.

  

  

