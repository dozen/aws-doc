[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks deregister-ecs-cluster:


**********************
deregister-ecs-cluster
**********************



===========
Description
===========



Deregisters a specified Amazon ECS cluster from a stack. For more information, see `Resource Management`_ .

 

**Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack or an attached policy that explicitly grants permissions. For more information on user permissions, see `<http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .



========
Synopsis
========

::

    deregister-ecs-cluster
  --ecs-cluster-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--ecs-cluster-arn`` (string)


  The cluster's ARN.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None

.. _Resource Management: http://docs.aws.amazon.com/opsworks/latest/userguide/workinglayers-ecscluster.html#workinglayers-ecscluster-delete
