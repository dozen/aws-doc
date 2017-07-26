[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks deregister-rds-db-instance:


**************************
deregister-rds-db-instance
**************************



===========
Description
===========



Deregisters an Amazon RDS instance.

 

 **Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/DeregisterRdsDbInstance>`_


========
Synopsis
========

::

    deregister-rds-db-instance
  --rds-db-instance-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--rds-db-instance-arn`` (string)


  The Amazon RDS instance's ARN.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To deregister an Amazon RDS DB instance from a stack**

The following example deregisters an RDS DB instance, identified by its ARN, from its stack. ::

  aws opsworks deregister-rds-db-instance --region us-east-1 --rds-db-instance-arn arn:aws:rds:us-west-2:123456789012:db:clitestdb

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