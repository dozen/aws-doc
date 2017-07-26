[ :ref:`aws <cli:aws>` . :ref:`opsworkscm <cli:aws opsworkscm>` ]

.. _cli:aws opsworkscm describe-backups:


****************
describe-backups
****************



===========
Description
===========



Describes backups. The results are ordered by time, with newest backups first. If you do not specify a backup-id or ServerName, the command returns all backups. 

 

This operation is synchronous. 

 

A ``ResourceNotFoundException`` is thrown when the backup does not exist. A ``ValidationException`` is raised when parameters of the request are not valid. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworkscm-2016-11-01/DescribeBackups>`_


========
Synopsis
========

::

    describe-backups
  [--backup-id <value>]
  [--server-name <value>]
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--backup-id`` (string)


  Describes a single backup. 

  

``--server-name`` (string)


  Returns backups for the server with the specified ServerName. 

  

``--next-token`` (string)


  next-token is a string that is returned in some command responses. It indicates that not all entries have been returned, and that you must run at least one more request to get remaining items. To get remaining results, call ``describe-backups`` again, and assign the token from the previous results as the value of the ``nextToken`` parameter. If there are no more results, the response object's ``nextToken`` parameter value is ``null`` . Setting a ``nextToken`` value that was not returned in your previous results causes an ``InvalidNextTokenException`` to occur.

  

``--max-results`` (integer)


  To receive a paginated response, use this parameter to specify the maximum number of results to be returned with a single call. If the number of available results exceeds this maximum, the response includes a ``next-token`` value that you can assign to the ``next-token`` request parameter to get the next set of results. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe backups**

The following ``describe-backups`` command returns information about all backups
associated with your account in your default region.::

  aws opsworks-cm describe-backups

The output for each backup entry returned by the command resembles the following.
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
         "Status": "Successful",
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

Backups -> (list)

  

  Contains the response to a ``describe-backups`` request. 

  

  (structure)

    

    Describes a single backup. 

    

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

      

      

    

  

NextToken -> (string)

  

  next-token is a string that is returned in some command responses. It indicates that not all entries have been returned, and that you must run at least one more request to get remaining items. To get remaining results, call ``describe-backups`` again, and assign the token from the previous results as the value of the ``nextToken`` parameter. If there are no more results, the response object's ``nextToken`` parameter value is ``null`` . Setting a ``nextToken`` value that was not returned in your previous results causes an ``InvalidNextTokenException`` to occur. 

  

  

