[ :ref:`aws <cli:aws>` . :ref:`opsworkscm <cli:aws opsworkscm>` ]

.. _cli:aws opsworkscm create-backup:


*************
create-backup
*************



===========
Description
===========



Creates an application-level backup of a server. While the server is in the ``BACKING_UP`` state, the server cannot be changed, and no additional backup can be created. 

 

Backups can be created for servers in ``RUNNING`` , ``HEALTHY`` , and ``UNHEALTHY`` states. By default, you can create a maximum of 50 manual backups. 

 

This operation is asynchronous. 

 

A ``LimitExceededException`` is thrown when the maximum number of manual backups is reached. An ``InvalidStateException`` is thrown when the server is not in any of the following states: RUNNING, HEALTHY, or UNHEALTHY. A ``ResourceNotFoundException`` is thrown when the server is not found. A ``ValidationException`` is thrown when parameters of the request are not valid. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworkscm-2016-11-01/CreateBackup>`_


========
Synopsis
========

::

    create-backup
  --server-name <value>
  [--description <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--server-name`` (string)


  The name of the server that you want to back up. 

  

``--description`` (string)


  A user-defined description of the backup. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create backups**

The following ``create-backup`` command starts a manual backup of a Chef Automate server
named ``automate-06`` in the ``us-east-1`` region. The command adds a descriptive message to
the backup in the ``--description`` parameter.::

  aws opsworks-cm create-backup --server-name 'automate-06' --description "state of my infrastructure at launch"

The output shows you information similar to the following about the new backup.
*Output*::

  {
   "Backups": [ 
      { 
         "BackupArn": "string",
         "BackupId": "automate-06-20160729133847520",
         "BackupType": "MANUAL",
         "CreatedAt": 2016-07-29T13:38:47.520Z,
         "Description": "state of my infrastructure at launch",
         "Engine": "Chef",
         "EngineModel": "Single",
         "EngineVersion": "12",
         "InstanceProfileArn": "arn:aws:iam::1019881987024:instance-profile/automate-06-1010V4UU2WRM2",
         "InstanceType": "m4.large",
         "KeyPair": "",
         "PreferredBackupWindow": "",
         "PreferredMaintenanceWindow": "",
         "S3LogUrl": "https://s3.amazonaws.com/automate-06/automate-06-20160729133847520",
         "SecurityGroupIds": [ "sg-1a24c270" ],
         "ServerName": "automate-06",
         "ServiceRoleArn": "arn:aws:iam::1019881987024:role/aws-opsworks-cm-service-role.1114810729735",
         "Status": "OK",
         "StatusDescription": "",
         "SubnetIds": [ "subnet-49436a18" ],
         "ToolsVersion": "string",
         "UserArn": "arn:aws:iam::1019881987024:user/opsworks-user"
      }
   ],
  }

**More Information**

For more information, see `Back Up and Restore an AWS OpsWorks for Chef Automate Server`_ in the *AWS OpsWorks User Guide*.

.. _`Back Up and Restore an AWS OpsWorks for Chef Automate Server`: http://docs.aws.amazon.com/opsworks/latest/userguide/opscm-backup-restore.html



======
Output
======

Backup -> (structure)

  

  Backup created by request.

  

  BackupArn -> (string)

    

    The ARN of the backup. 

    

    

  BackupId -> (string)

    

    The generated ID of the backup. Example: ``myServerName-yyyyMMddHHmmssSSS``  

    

    

  BackupType -> (string)

    

    The backup type. Valid values are ``automated`` or ``manual`` . 

    

    

  CreatedAt -> (timestamp)

    

    The time stamp when the backup was created in the database. Example: ``2016-07-29T13:38:47.520Z``  

    

    

  Description -> (string)

    

    A user-provided description for a manual backup. This field is empty for automated backups. 

    

    

  Engine -> (string)

    

    The engine type that is obtained from the server when the backup is created. 

    

    

  EngineModel -> (string)

    

    The engine model that is obtained from the server when the backup is created. 

    

    

  EngineVersion -> (string)

    

    The engine version that is obtained from the server when the backup is created. 

    

    

  InstanceProfileArn -> (string)

    

    The EC2 instance profile ARN that is obtained from the server when the backup is created. Because this value is stored, you are not required to provide the InstanceProfileArn again if you restore a backup. 

    

    

  InstanceType -> (string)

    

    The instance type that is obtained from the server when the backup is created. 

    

    

  KeyPair -> (string)

    

    The key pair that is obtained from the server when the backup is created. 

    

    

  PreferredBackupWindow -> (string)

    

    The preferred backup period that is obtained from the server when the backup is created. 

    

    

  PreferredMaintenanceWindow -> (string)

    

    The preferred maintenance period that is obtained from the server when the backup is created. 

    

    

  S3DataSize -> (integer)

    

    This field is deprecated and is no longer used. 

    

    

  S3DataUrl -> (string)

    

    This field is deprecated and is no longer used. 

    

    

  S3LogUrl -> (string)

    

    The Amazon S3 URL of the backup's log file. 

    

    

  SecurityGroupIds -> (list)

    

    The security group IDs that are obtained from the server when the backup is created. 

    

    (string)

      

      

    

  ServerName -> (string)

    

    The name of the server from which the backup was made. 

    

    

  ServiceRoleArn -> (string)

    

    The service role ARN that is obtained from the server when the backup is created. 

    

    

  Status -> (string)

    

    The status of a backup while in progress. 

    

    

  StatusDescription -> (string)

    

    An informational message about backup status. 

    

    

  SubnetIds -> (list)

    

    The subnet IDs that are obtained from the server when the backup is created. 

    

    (string)

      

      

    

  ToolsVersion -> (string)

    

    The version of AWS OpsWorks for Chef Automate-specific tools that is obtained from the server when the backup is created. 

    

    

  UserArn -> (string)

    

    The IAM user ARN of the requester for manual backups. This field is empty for automated backups. 

    

    

  

