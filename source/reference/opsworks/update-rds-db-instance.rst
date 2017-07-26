[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks update-rds-db-instance:


**********************
update-rds-db-instance
**********************



===========
Description
===========



Updates an Amazon RDS instance.

 

 **Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/UpdateRdsDbInstance>`_


========
Synopsis
========

::

    update-rds-db-instance
  --rds-db-instance-arn <value>
  [--db-user <value>]
  [--db-password <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rds-db-instance-arn`` (string)


  The Amazon RDS instance's ARN.

  

``--db-user`` (string)


  The master user name.

  

``--db-password`` (string)


  The database password.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To update a registered Amazon RDS DB instance**

The following example updates an Amazon RDS instance's master password value.
Note that this command does not change the RDS instance's master password, just the password that
you provide to AWS OpsWorks.
If this password does not match the RDS instance's password,
your application will not be able to connect to the database. ::

  aws opsworks --region us-east-1 update-rds-db-instance --db-password 123456789

*Output*: None.

**More Information**

For more information, see `Registering Amazon RDS Instances with a Stack`_ in the *AWS OpsWorks User Guide*.

.. _`Registering Amazon RDS Instances with a Stack`: http://docs.aws.amazon.com/opsworks/latest/userguide/resources-reg.html#resources-reg-rds



======
Output
======

None