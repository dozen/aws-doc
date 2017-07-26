[ :ref:`aws <cli:aws>` . :ref:`cognito-idp <cli:aws cognito-idp>` ]

.. _cli:aws cognito-idp start-user-import-job:


*********************
start-user-import-job
*********************



===========
Description
===========



Starts the user import.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/cognito-idp-2016-04-18/StartUserImportJob>`_


========
Synopsis
========

::

    start-user-import-job
  --user-pool-id <value>
  --job-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--user-pool-id`` (string)


  The user pool ID for the user pool that the users are being imported into.

  

``--job-id`` (string)


  The job ID for the user import job.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

UserImportJob -> (structure)

  

  The job object that represents the user import job.

  

  JobName -> (string)

    

    The job name for the user import job.

    

    

  JobId -> (string)

    

    The job ID for the user import job.

    

    

  UserPoolId -> (string)

    

    The user pool ID for the user pool that the users are being imported into.

    

    

  PreSignedUrl -> (string)

    

    The pre-signed URL to be used to upload the ``.csv`` file.

    

    

  CreationDate -> (timestamp)

    

    The date the user import job was created.

    

    

  StartDate -> (timestamp)

    

    The date when the user import job was started.

    

    

  CompletionDate -> (timestamp)

    

    The date when the user import job was completed.

    

    

  Status -> (string)

    

    The status of the user import job. One of the following:

     

     
    * ``Created`` - The job was created but not started. 
     
    * ``Pending`` - A transition state. You have started the job, but it has not begun importing users yet. 
     
    * ``InProgress`` - The job has started, and users are being imported. 
     
    * ``Stopping`` - You have stopped the job, but the job has not stopped importing users yet. 
     
    * ``Stopped`` - You have stopped the job, and the job has stopped importing users. 
     
    * ``Succeeded`` - The job has completed successfully. 
     
    * ``Failed`` - The job has stopped due to an error. 
     
    * ``Expired`` - You created a job, but did not start the job within 24-48 hours. All data associated with the job was deleted, and the job cannot be started. 
     

    

    

  CloudWatchLogsRoleArn -> (string)

    

    The role ARN for the Amazon CloudWatch Logging role for the user import job. For more information, see "Creating the CloudWatch Logs IAM Role" in the Amazon Cognito Developer Guide.

    

    

  ImportedUsers -> (long)

    

    The number of users that were successfully imported.

    

    

  SkippedUsers -> (long)

    

    The number of users that were skipped.

    

    

  FailedUsers -> (long)

    

    The number of users that could not be imported.

    

    

  CompletionMessage -> (string)

    

    The message returned when the user import job is completed.

    

    

  

