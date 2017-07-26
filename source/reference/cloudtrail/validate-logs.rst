[ :ref:`aws <cli:aws>` . :ref:`cloudtrail <cli:aws cloudtrail>` ]

.. _cli:aws cloudtrail validate-logs:


*************
validate-logs
*************



===========
Description
===========


    Validates CloudTrail logs for a given period of time.

    This command uses the digest files delivered to your S3 bucket to perform
    the validation.

    The AWS CLI allows you to detect the following types of changes:

    - Modification or deletion of CloudTrail log files.
    - Modification or deletion of CloudTrail digest files.

    To validate log files with the AWS CLI, the following preconditions must
    be met:

    - You must have online connectivity to AWS.
    - You must have read access to the S3 bucket that contains the digest and
      log files.
    - The digest and log files must not have been moved from the original S3
      location where CloudTrail delivered them.

    When you disable Log File Validation, the chain of digest files is broken
    after one hour. CloudTrail will not digest log files that were delivered
    during a period in which the Log File Validation feature was disabled.
    For example, if you enable Log File Validation on January 1, disable it
    on January 2, and re-enable it on January 10, digest files will not be
    created for the log files delivered from January 3 to January 9. The same
    applies whenever you stop CloudTrail logging or delete a trail.

    .. note::

        Log files that have been downloaded to local disk cannot be validated
        with the AWS CLI. The CLI will download all log files each time this
        command is executed.

    .. note::

        This command requires that the role executing the command has
        permission to call ListObjects, GetObject, and GetBucketLocation for
        each bucket referenced by the trail.

    



========
Synopsis
========

::

    validate-logs
  --trail-arn <value>
  --start-time <value>
  [--end-time <value>]
  [--s3-bucket <value>]
  [--s3-prefix <value>]
  [--verbose]




=======
Options
=======

``--trail-arn`` (string)
Specifies the ARN of the trail to be validated

``--start-time`` (string)
Specifies that log files delivered on or after the specified UTC timestamp value will be validated. Example: "2015-01-08T05:21:42Z".

``--end-time`` (string)
Optionally specifies that log files delivered on or before the specified UTC timestamp value will be validated. The default value is the current time. Example: "2015-01-08T12:31:41Z".

``--s3-bucket`` (string)
Optionally specifies the S3 bucket where the digest files are stored. If a bucket name is not specified, the CLI will retrieve it by calling describe_trails

``--s3-prefix`` (string)
Optionally specifies the optional S3 prefix where the digest files are stored. If not specified, the CLI will determine the prefix automatically by calling describe_trails.

``--verbose`` (boolean)
Display verbose log validation information

