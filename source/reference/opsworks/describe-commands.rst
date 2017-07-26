[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks describe-commands:


*****************
describe-commands
*****************



===========
Description
===========



Describes the results of specified commands.

 

.. note::

   

  This call accepts only one resource-identifying parameter.

   

 

 **Required Permissions** : To use this action, an IAM user must have a Show, Deploy, or Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/DescribeCommands>`_


========
Synopsis
========

::

    describe-commands
  [--deployment-id <value>]
  [--instance-id <value>]
  [--command-ids <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--deployment-id`` (string)


  The deployment ID. If you include this parameter, ``describe-commands`` returns a description of the commands associated with the specified deployment.

  

``--instance-id`` (string)


  The instance ID. If you include this parameter, ``describe-commands`` returns a description of the commands associated with the specified instance.

  

``--command-ids`` (list)


  An array of command IDs. If you include this parameter, ``describe-commands`` returns a description of the specified commands. Otherwise, it returns a description of every command.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe commands**

The following ``describe-commands`` commmand describes the commands in a specified instance. ::

  aws opsworks --region us-east-1 describe-commands --instance-id 8c2673b9-3fe5-420d-9cfa-78d875ee7687

*Output*::

  {
    "Commands": [
      {
        "Status": "successful",
        "CompletedAt": "2013-07-25T18:57:47+00:00",
        "InstanceId": "8c2673b9-3fe5-420d-9cfa-78d875ee7687",
        "DeploymentId": "6ed0df4c-9ef7-4812-8dac-d54a05be1029",
        "AcknowledgedAt": "2013-07-25T18:57:41+00:00",
        "LogUrl": "https://s3.amazonaws.com/prod_stage-log/logs/008c1a91-ec59-4d51-971d-3adff54b00cc?AWSAccessKeyId=AKIAIOSFODNN7EXAMPLE &Expires=1375394373&Signature=HkXil6UuNfxTCC37EPQAa462E1E%3D&response-cache-control=private&response-content-encoding=gzip&response-content- type=text%2Fplain",
        "Type": "undeploy",
        "CommandId": "008c1a91-ec59-4d51-971d-3adff54b00cc",
        "CreatedAt": "2013-07-25T18:57:34+00:00",
        "ExitCode": 0
      },
      {
        "Status": "successful",
        "CompletedAt": "2013-07-25T18:55:40+00:00",
        "InstanceId": "8c2673b9-3fe5-420d-9cfa-78d875ee7687",
        "DeploymentId": "19d3121e-d949-4ff2-9f9d-94eac087862a",
        "AcknowledgedAt": "2013-07-25T18:55:32+00:00",
        "LogUrl": "https://s3.amazonaws.com/prod_stage-log/logs/899d3d64-0384-47b6-a586-33433aad117c?AWSAccessKeyId=AKIAIOSFODNN7EXAMPLE &Expires=1375394373&Signature=xMsJvtLuUqWmsr8s%2FAjVru0BtRs%3D&response-cache-control=private&response-content-encoding=gzip&response-conten t-type=text%2Fplain",
        "Type": "deploy",
        "CommandId": "899d3d64-0384-47b6-a586-33433aad117c",
        "CreatedAt": "2013-07-25T18:55:29+00:00",
        "ExitCode": 0
      }
    ]
  }

**More Information**

For more information, see `AWS OpsWorks Lifecycle Events`_ in the *AWS OpsWorks User Guide*.

.. _`AWS OpsWorks Lifecycle Events`: http://docs.aws.amazon.com/opsworks/latest/userguide/workingcookbook-events.html



======
Output
======

Commands -> (list)

  

  An array of ``Command`` objects that describe each of the specified commands.

  

  (structure)

    

    Describes a command.

    

    CommandId -> (string)

      

      The command ID.

      

      

    InstanceId -> (string)

      

      The ID of the instance where the command was executed.

      

      

    DeploymentId -> (string)

      

      The command deployment ID.

      

      

    CreatedAt -> (string)

      

      Date and time when the command was run.

      

      

    AcknowledgedAt -> (string)

      

      Date and time when the command was acknowledged.

      

      

    CompletedAt -> (string)

      

      Date when the command completed.

      

      

    Status -> (string)

      

      The command status:

       

       
      * failed 
       
      * successful 
       
      * skipped 
       
      * pending 
       

      

      

    ExitCode -> (integer)

      

      The command exit code.

      

      

    LogUrl -> (string)

      

      The URL of the command log.

      

      

    Type -> (string)

      

      The command type:

       

       
      * ``configure``   
       
      * ``deploy``   
       
      * ``execute_recipes``   
       
      * ``install_dependencies``   
       
      * ``restart``   
       
      * ``rollback``   
       
      * ``setup``   
       
      * ``start``   
       
      * ``stop``   
       
      * ``undeploy``   
       
      * ``update_custom_cookbooks``   
       
      * ``update_dependencies``   
       

      

      

    

  

