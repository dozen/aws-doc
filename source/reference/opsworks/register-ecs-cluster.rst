[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks register-ecs-cluster:


********************
register-ecs-cluster
********************



===========
Description
===========



Registers a specified Amazon ECS cluster with a stack. You can register only one cluster with a stack. A cluster can be registered with only one stack. For more information, see `Resource Management <http://docs.aws.amazon.com/opsworks/latest/userguide/workinglayers-ecscluster.html>`_ .

 

 **Required Permissions** : To use this action, an IAM user must have a Manage permissions level for the stack or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/RegisterEcsCluster>`_


========
Synopsis
========

::

    register-ecs-cluster
  --ecs-cluster-arn <value>
  --stack-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--ecs-cluster-arn`` (string)


  The cluster's ARN.

  

``--stack-id`` (string)


  The stack ID.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

EcsClusterArn -> (string)

  

  The cluster's ARN.

  

  

