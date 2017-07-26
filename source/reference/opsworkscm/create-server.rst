[ :ref:`aws <cli:aws>` . :ref:`opsworkscm <cli:aws opsworkscm>` ]

.. _cli:aws opsworkscm create-server:


*************
create-server
*************



===========
Description
===========



Creates and immedately starts a new server. The server is ready to use when it is in the ``HEALTHY`` state. By default, you can create a maximum of 10 servers. 

 

This operation is asynchronous. 

 

A ``LimitExceededException`` is thrown when you have created the maximum number of servers (10). A ``ResourceAlreadyExistsException`` is thrown when a server with the same name already exists in the account. A ``ResourceNotFoundException`` is thrown when you specify a backup ID that is not valid or is for a backup that does not exist. A ``ValidationException`` is thrown when parameters of the request are not valid. 

 

If you do not specify a security group by adding the ``SecurityGroupIds`` parameter, AWS OpsWorks creates a new security group. The default security group opens the Chef server to the world on TCP port 443. If a KeyName is present, AWS OpsWorks enables SSH access. SSH is also open to the world on TCP port 22. 

 

By default, the Chef Server is accessible from any IP address. We recommend that you update your security group rules to allow access from known IP addresses and address ranges only. To edit security group rules, open Security Groups in the navigation pane of the EC2 management console. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworkscm-2016-11-01/CreateServer>`_


========
Synopsis
========

::

    create-server
  [--associate-public-ip-address | --no-associate-public-ip-address]
  [--disable-automated-backup | --no-disable-automated-backup]
  [--engine <value>]
  [--engine-model <value>]
  [--engine-version <value>]
  [--engine-attributes <value>]
  [--backup-retention-count <value>]
  --server-name <value>
  --instance-profile-arn <value>
  --instance-type <value>
  [--key-pair <value>]
  [--preferred-maintenance-window <value>]
  [--preferred-backup-window <value>]
  [--security-group-ids <value>]
  --service-role-arn <value>
  [--subnet-ids <value>]
  [--backup-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--associate-public-ip-address`` | ``--no-associate-public-ip-address`` (boolean)


  Associate a public IP address with a server that you are launching. Valid values are ``true`` or ``false`` . The default value is ``true`` . 

  

``--disable-automated-backup`` | ``--no-disable-automated-backup`` (boolean)


  Enable or disable scheduled backups. Valid values are ``true`` or ``false`` . The default value is ``true`` . 

  

``--engine`` (string)


  The configuration management engine to use. Valid values include ``Chef`` . 

  

``--engine-model`` (string)


  The engine model, or option. Valid values include ``Single`` . 

  

``--engine-version`` (string)


  The major release version of the engine that you want to use. Values depend on the engine that you choose. 

  

``--engine-attributes`` (list)


  Optional engine attributes on a specified server. 

   

   **Attributes accepted in a createServer request:**  

   

   
  * ``CHEF_PIVOTAL_KEY`` : A base64-encoded RSA private key that is not stored by AWS OpsWorks for Chef. This private key is required to access the Chef API. When no CHEF_PIVOTAL_KEY is set, one is generated and returned in the response.  
   
  * ``CHEF_DELIVERY_ADMIN_PASSWORD`` : The password for the administrative user in the Chef Automate GUI. The password length is a minimum of eight characters, and a maximum of 32. The password can contain letters, numbers, and special characters (!/@#$%^+=_). The password must contain at least one lower case letter, one upper case letter, one number, and one special character. When no CHEF_DELIVERY_ADMIN_PASSWORD is set, one is generated and returned in the response. 
   

  



Shorthand Syntax::

    Name=string,Value=string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Value": "string"
    }
    ...
  ]



``--backup-retention-count`` (integer)


  The number of automated backups that you want to keep. Whenever a new backup is created, AWS OpsWorks for Chef Automate deletes the oldest backups if this number is exceeded. The default value is ``1`` . 

  

``--server-name`` (string)


  The name of the server. The server name must be unique within your AWS account, within each region. Server names must start with a letter; then letters, numbers, or hyphens (-) are allowed, up to a maximum of 40 characters. 

  

``--instance-profile-arn`` (string)


  The ARN of the instance profile that your Amazon EC2 instances use. Although the AWS OpsWorks console typically creates the instance profile for you, if you are using API commands instead, run the service-role-creation.yaml AWS CloudFormation template, located at https://s3.amazonaws.com/opsworks-cm-us-east-1-prod-default-assets/misc/opsworks-cm-roles.yaml. This template creates a CloudFormation stack that includes the instance profile you need. 

  

``--instance-type`` (string)


  The Amazon EC2 instance type to use. Valid values must be specified in the following format: ``^([cm][34]|t2).*`` For example, ``m4.large`` . Valid values are ``t2.medium`` , ``m4.large`` , or ``m4.2xlarge`` . 

  

``--key-pair`` (string)


  The Amazon EC2 key pair to set for the instance. This parameter is optional; if desired, you may specify this parameter to connect to your instances by using SSH. 

  

``--preferred-maintenance-window`` (string)


  The start time for a one-hour period each week during which AWS OpsWorks for Chef Automate performs maintenance on the instance. Valid values must be specified in the following format: ``DDD:HH:MM`` . The specified time is in coordinated universal time (UTC). The default value is a random one-hour period on Tuesday, Wednesday, or Friday. See ``preferred-maintenance-window`` for more information. 

   

   **Example:**  ``Mon:08:00`` , which represents a start time of every Monday at 08:00 UTC. (8:00 a.m.) 

  

``--preferred-backup-window`` (string)


  The start time for a one-hour period during which AWS OpsWorks for Chef Automate backs up application-level data on your server if automated backups are enabled. Valid values must be specified in one of the following formats: 

   

   
  * ``HH:MM`` for daily backups 
   
  * ``DDD:HH:MM`` for weekly backups 
   

   

  The specified time is in coordinated universal time (UTC). The default value is a random, daily start time.

   

   **Example:**  ``08:00`` , which represents a daily start time of 08:00 UTC.

   

   **Example:**  ``Mon:08:00`` , which represents a start time of every Monday at 08:00 UTC. (8:00 a.m.)

  

``--security-group-ids`` (list)


  A list of security group IDs to attach to the Amazon EC2 instance. If you add this parameter, the specified security groups must be within the VPC that is specified by ``SubnetIds`` . 

   

  If you do not specify this parameter, AWS OpsWorks for Chef Automate creates one new security group that uses TCP ports 22 and 443, open to 0.0.0.0/0 (everyone). 

  



Syntax::

  "string" "string" ...



``--service-role-arn`` (string)


  The service role that the AWS OpsWorks for Chef Automate service backend uses to work with your account. Although the AWS OpsWorks management console typically creates the service role for you, if you are using the AWS CLI or API commands, run the service-role-creation.yaml AWS CloudFormation template, located at https://s3.amazonaws.com/opsworks-stuff/latest/service-role-creation.yaml. This template creates a CloudFormation stack that includes the service role that you need. 

  

``--subnet-ids`` (list)


  The IDs of subnets in which to launch the server EC2 instance. 

   

  Amazon EC2-Classic customers: This field is required. All servers must run within a VPC. The VPC must have "Auto Assign Public IP" enabled. 

   

  EC2-VPC customers: This field is optional. If you do not specify subnet IDs, your EC2 instances are created in a default subnet that is selected by Amazon EC2. If you specify subnet IDs, the VPC must have "Auto Assign Public IP" enabled. 

   

  For more information about supported Amazon EC2 platforms, see `Supported Platforms <http://docs.aws.amazon.com/https:/docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-supported-platforms.html>`_ .

  



Syntax::

  "string" "string" ...



``--backup-id`` (string)


  If you specify this field, AWS OpsWorks for Chef Automate creates the server by using the backup represented by BackupId. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a server**

The following ``create-server`` command creates a new Chef Automate server
named ``automate-06`` in your default region. Note that defaults are used for
most other settings, such as number of backups to retain, and maintenance and backup
start times. Before you run a ``create-server`` command, complete prerequisites in
.. _`Getting Started with AWS OpsWorks for Chef Automate`: http://docs.aws.amazon.com/opsworks/latest/userguide/gettingstarted-opscm.html
.::

  aws opsworks-cm create-server --engine "Chef" --engine-model "Single" --engine-version "12" --server-name "automate-06" --instance-profile-arn "arn:aws:iam::1019881987024:instance-profile/aws-opsworks-cm-ec2-role" --instance-type "t2.medium" --key-pair "amazon-test" --service-role-arn "arn:aws:iam::044726508045:role/aws-opsworks-cm-service-role"

The output shows you information similar to the following about the new server.
*Output*::

  {
   "Server": { 
      "BackupRetentionCount": 10,
      "CreatedAt": 2016-07-29T13:38:47.520Z,
      "DisableAutomatedBackup": FALSE,
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
      "InstanceProfileArn": "arn:aws:iam::1019881987024:instance-profile/aws-opsworks-cm-ec2-role",
      "InstanceType": "t2.medium",
      "KeyPair": "amazon-test",
      "MaintenanceStatus": "",
      "PreferredBackupWindow": "Sun:02:00",
      "PreferredMaintenanceWindow": "00:00",
      "SecurityGroupIds": [ "sg-1a24c270" ],
      "ServerArn": "arn:aws:iam::1019881987024:instance/automate-06-1010V4UU2WRM2",
      "ServerName": "automate-06",
      "ServiceRoleArn": "arn:aws:iam::1019881987024:role/aws-opsworks-cm-service-role",
      "Status": "CREATING",
      "StatusReason": "",
      "SubnetIds": [ "subnet-49436a18" ]
   }
}

**More Information**

For more information, see `UpdateServer`_ in the *AWS OpsWorks for Chef Automate API Reference*.

.. _`UpdateServer`: http://docs.aws.amazon.com/opsworks-cm/latest/APIReference/API_UpdateServer.html



======
Output
======

Server -> (structure)

  

  The server that is created by the request. 

  

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

    

    

  

