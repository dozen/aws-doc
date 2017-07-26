[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks describe-rds-db-instances:


*************************
describe-rds-db-instances
*************************



===========
Description
===========



Describes Amazon RDS instances.

 

**Required Permissions** : To use this action, an IAM user must have a Show, Deploy, or Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    describe-rds-db-instances
  --stack-id <value>
  [--rds-db-instance-arns <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--stack-id`` (string)


  The stack ID that the instances are registered with. The operation returns descriptions of all registered Amazon RDS instances.

  

``--rds-db-instance-arns`` (list)


  An array containing the ARNs of the instances to be described.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe a stack's registered Amazon RDS instances**

The following example describes the Amazon RDS instances registered with a specified stack. ::

  aws opsworks --region us-east-1 describe-rds-db-instances --stack-id d72553d4-8727-448c-9b00-f024f0ba1b06

**Note**: AWS OpsWorks CLI commands should set the region to ``us-east-1`` regardless of the stack's location.

*Output*: The following is the output for a stack with one registered RDS instance. ::

  {
    "RdsDbInstances": [
      {
        "Engine": "mysql", 
        "StackId": "d72553d4-8727-448c-9b00-f024f0ba1b06", 
        "MissingOnRds": false, 
        "Region": "us-west-2", 
        "RdsDbInstanceArn": "arn:aws:rds:us-west-2:123456789012:db:clitestdb", 
        "DbPassword": "*****FILTERED*****", 
        "Address": "clitestdb.cdlqlk5uwd0k.us-west-2.rds.amazonaws.com", 
        "DbUser": "cliuser", 
        "DbInstanceIdentifier": "clitestdb"
      }
    ]
  }


For more information, see `Resource Management`_ in the *AWS OpsWorks User Guide*.

.. _`Resource Management`: http://docs.aws.amazon.com/opsworks/latest/userguide/resources.html



======
Output
======

RdsDbInstances -> (list)

  

  An a array of ``RdsDbInstance`` objects that describe the instances.

  

  (structure)

    

    Describes an Amazon RDS instance.

    

    RdsDbInstanceArn -> (string)

      

      The instance's ARN.

      

      

    DbInstanceIdentifier -> (string)

      

      The DB instance identifier.

      

      

    DbUser -> (string)

      

      The master user name.

      

      

    DbPassword -> (string)

      

      AWS OpsWorks returns ``*****FILTERED*****`` instead of the actual value.

      

      

    Region -> (string)

      

      The instance's AWS region.

      

      

    Address -> (string)

      

      The instance's address.

      

      

    Engine -> (string)

      

      The instance's database engine.

      

      

    StackId -> (string)

      

      The ID of the stack that the instance is registered with.

      

      

    MissingOnRds -> (boolean)

      

      Set to ``true`` if AWS OpsWorks was unable to discover the Amazon RDS instance. AWS OpsWorks attempts to discover the instance only once. If this value is set to ``true`` , you must deregister the instance and then register it again.

      

      

    

  



.. _Managing User Permissions: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html
