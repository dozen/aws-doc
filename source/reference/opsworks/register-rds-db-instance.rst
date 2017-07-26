[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks register-rds-db-instance:


************************
register-rds-db-instance
************************



===========
Description
===========



Registers an Amazon RDS instance with a stack.

 

 **Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/RegisterRdsDbInstance>`_


========
Synopsis
========

::

    register-rds-db-instance
  --stack-id <value>
  --rds-db-instance-arn <value>
  --db-user <value>
  --db-password <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--stack-id`` (string)


  The stack ID.

  

``--rds-db-instance-arn`` (string)


  The Amazon RDS instance's ARN.

  

``--db-user`` (string)


  The database's master user name.

  

``--db-password`` (string)


  The database password.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To register an Amazon RDS instance with a stack**

The following example registers an Amazon RDS DB instance, identified by its Amazon Resource Name (ARN), with a specified stack.
It also specifies the instance's master username and password. Note that AWS OpsWorks does not validate either of these
values. If either one is incorrect, your application will not be able to connect to the database. ::

  aws opsworks register-rds-db-instance --region us-east-1 --stack-id d72553d4-8727-448c-9b00-f024f0ba1b06 --rds-db-instance-arn arn:aws:rds:us-west-2:123456789012:db:clitestdb  --db-user cliuser --db-password some23!pwd

*Output*: None.

**More Information**

For more information, see `Registering Amazon RDS Instances with a Stack`_ in the *AWS OpsWorks User Guide*.

.. _`Registering Amazon RDS Instances with a Stack`: http://docs.aws.amazon.com/opsworks/latest/userguide/resources-reg.html#resources-reg-rds


======
Output
======

None