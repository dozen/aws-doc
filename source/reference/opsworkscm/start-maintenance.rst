[ :ref:`aws <cli:aws>` . :ref:`opsworkscm <cli:aws opsworkscm>` ]

.. _cli:aws opsworkscm start-maintenance:


*****************
start-maintenance
*****************



===========
Description
===========



Manually starts server maintenance. This command can be useful if an earlier maintenance attempt failed, and the underlying cause of maintenance failure has been resolved. The server is in an ``UNDER_MAINTENANCE`` state while maintenance is in progress. 

 

Maintenance can only be started on servers in ``HEALTHY`` and ``UNHEALTHY`` states. Otherwise, an ``InvalidStateException`` is thrown. A ``ResourceNotFoundException`` is thrown when the server does not exist. A ``ValidationException`` is raised when parameters of the request are not valid. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworkscm-2016-11-01/StartMaintenance>`_


========
Synopsis
========

::

    start-maintenance
  --server-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--server-name`` (string)


  The name of the server on which to run maintenance. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To start maintenance**

The following ``start-maintenance`` command manually starts maintenance on a Chef Automate server 
named ``automate-06`` in your default region. This command can be useful if an earlier, automated 
maintenance attempt failed, and the underlying cause of maintenance failure has been resolved.::

  aws opsworks-cm start-maintenance --server-name 'automate-06'

The output shows you information similar to the following about the maintenance request.
*Output*::

  {
   "Server": { 
      "BackupRetentionCount": 8,
      "CreatedAt": 2016-07-29T13:38:47.520Z,
      "DisableAutomatedBackup": TRUE,
      "Endpoint": "https://opsworks-cm.us-east-1.amazonaws.com",
      "Engine": "Chef",
      "EngineAttributes": [ 
         { 
            "Name": "CHEF_DELIVERY_ADMIN_PASSWORD",
            "Value": "1Password1"
         }
      ],
      "EngineModel": "Single",
      "EngineVersion": "12",
      "InstanceProfileArn": "arn:aws:iam::1019881987024:instance-profile/automate-06-1010V4UU2WRM2",
      "InstanceType": "m4.large",
      "KeyPair": "",
      "MaintenanceStatus": "SUCCESS",
      "PreferredBackupWindow": "",
      "PreferredMaintenanceWindow": "",
      "SecurityGroupIds": [ "sg-1a24c270" ],
      "ServerArn": "arn:aws:iam::1019881987024:instance/automate-06-1010V4UU2WRM2",
      "ServerName": "automate-06",
      "ServiceRoleArn": "arn:aws:iam::1019881987024:role/aws-opsworks-cm-service-role.1114810729735",
      "Status": "HEALTHY",
      "StatusReason": "",
      "SubnetIds": [ "subnet-49436a18" ]
   }
}

**More Information**

For more information, see `StartMaintenance`_ in the *AWS OpsWorks for Chef Automate API Reference*.

.. _`StartMaintenance`: http://docs.aws.amazon.com/opsworks-cm/latest/APIReference/API_StartMaintenance.html



======
Output
======

Server -> (structure)

  

  Contains the response to a ``start-maintenance`` request. 

  

  AssociatePublicIpAddress -> (boolean)

    

    Associate a public IP address with a server that you are launching. 

    

    

  BackupRetentionCount -> (integer)

    

    The number of automated backups to keep. 

    

    

  ServerName -> (string)

    

    The name of the server. 

    

    

  CreatedAt -> (timestamp)

    

    Time stamp of server creation. Example ``2016-07-29T13:38:47.520Z``  

    

    

  CloudFormationStackArn -> (string)

    

    The ARN of the CloudFormation stack that was used to create the server. 

    

    

  DisableAutomatedBackup -> (boolean)

    

    Disables automated backups. The number of stored backups is dependent on the value of PreferredBackupCount. 

    

    

  Endpoint -> (string)

    

    A DNS name that can be used to access the engine. Example: ``myserver-asdfghjkl.us-east-1.opsworks.io``  

    

    

  Engine -> (string)

    

    The engine type of the server. The valid value in this release is ``Chef`` . 

    

    

  EngineModel -> (string)

    

    The engine model of the server. The valid value in this release is ``Single`` . 

    

    

  EngineAttributes -> (list)

    

    The response of a createServer() request returns the master credential to access the server in EngineAttributes. These credentials are not stored by AWS OpsWorks for Chef Automate; they are returned only as part of the result of createServer(). 

     

     **Attributes returned in a createServer response:**  

     

     
    * ``CHEF_PIVOTAL_KEY`` : A base64-encoded RSA private key that is generated by AWS OpsWorks for Chef Automate. This private key is required to access the Chef API. 
     
    * ``CHEF_STARTER_KIT`` : A base64-encoded ZIP file. The ZIP file contains a Chef starter kit, which includes a README, a configuration file, and the required RSA private key. Save this file, unzip it, and then change to the directory where you've unzipped the file contents. From this directory, you can run Knife commands. 
     

    

    (structure)

      

      A name and value pair that is specific to the engine of the server. 

      

      Name -> (string)

        

        The name of the engine attribute. 

        

        

      Value -> (string)

        

        The value of the engine attribute. 

        

        

      

    

  EngineVersion -> (string)

    

    The engine version of the server. Because Chef is the engine available in this release, the valid value for EngineVersion is ``12`` . 

    

    

  InstanceProfileArn -> (string)

    

    The instance profile ARN of the server. 

    

    

  InstanceType -> (string)

    

    The instance type for the server, as specified in the CloudFormation stack. This might not be the same instance type that is shown in the EC2 console. 

    

    

  KeyPair -> (string)

    

    The key pair associated with the server. 

    

    

  MaintenanceStatus -> (string)

    

    The status of the most recent server maintenance run. Shows ``SUCCESS`` or ``FAILED`` . 

    

    

  PreferredMaintenanceWindow -> (string)

    

    The preferred maintenance period specified for the server. 

    

    

  PreferredBackupWindow -> (string)

    

    The preferred backup period specified for the server. 

    

    

  SecurityGroupIds -> (list)

    

    The security group IDs for the server, as specified in the CloudFormation stack. These might not be the same security groups that are shown in the EC2 console. 

    

    (string)

      

      

    

  ServiceRoleArn -> (string)

    

    The service role ARN used to create the server. 

    

    

  Status -> (string)

    

    The server's status. This field displays the states of actions in progress, such as creating, running, or backing up the server, as well as the server's health state. 

    

    

  StatusReason -> (string)

    

    Depending on the server status, this field has either a human-readable message (such as a create or backup error), or an escaped block of JSON (used for health check results). 

    

    

  SubnetIds -> (list)

    

    The subnet IDs specified in a create-server request. 

    

    (string)

      

      

    

  ServerArn -> (string)

    

    The ARN of the server. 

    

    

  

