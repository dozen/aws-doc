[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks deregister-rds-db-instance:


**************************
deregister-rds-db-instance
**************************



===========
Description
===========



Deregisters an Amazon RDS instance.

 

**Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    deregister-rds-db-instance
  --rds-db-instance-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--rds-db-instance-arn`` (string)


  The Amazon RDS instance's ARN.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To deregister an Amazon RDS DB instance from a stack**

The following example deregisters an RDS DB instance, identified by its ARN, from its stack. ::

  aws opsworks deregister-rds-db-instance --region us-east-1 --rds-db-instance-arn arn:aws:rds:us-west-2:123456789012:db:clitestdb

**Note**: AWS OpsWorks CLI commands should set the region to ``us-east-1`` regardless of the stack's location.

*Output*: None.

**More Information**

For more information, see `Deregistering Amazon RDS Instances`_ in the *ASW OpsWorks User Guide*.

.. _`Deregistering Amazon RDS Instances`: http://docs.aws.amazon.com/opsworks/latest/userguide/resources-dereg.html#resources-dereg-rds


.. instance ID: clitestdb
   Master usernams: cliuser
   Master PWD: some23!pwd
   DB Name: mydb
   aws opsworks deregister-rds-db-instance --region us-east-1 --rds-db-instance-arn arn:aws:rds:us-west-2:645732743964:db:clitestdb

======
Output
======

None

.. _Managing User Permissions: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html
