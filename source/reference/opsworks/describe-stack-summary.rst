[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks describe-stack-summary:


**********************
describe-stack-summary
**********************



===========
Description
===========



Describes the number of layers and apps in a specified stack, and the number of instances in each state, such as ``running_setup`` or ``online`` .

 

**Required Permissions** : To use this action, an IAM user must have a Show, Deploy, or Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    describe-stack-summary
  --stack-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--stack-id`` (string)


  The stack ID.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe a stack's configuration**

The following ``describe-stack-summary`` command returns a summary of the specified stack's configuration. ::

  aws opsworks --region us-east-1 describe-stack-summary --stack-id 8c428b08-a1a1-46ce-a5f8-feddc43771b8

**Note**: AWS OpsWorks CLI commands should set the region to ``us-east-1`` regardless of the stack's location.

*Output*::

  {
    "StackSummary": {
      "StackId": "8c428b08-a1a1-46ce-a5f8-feddc43771b8",
      "InstancesCount": {
        "Booting": 1
      },
      "Name": "CLITest",
      "AppsCount": 1,
      "LayersCount": 1,
      "Arn": "arn:aws:opsworks:us-west-2:123456789012:stack/8c428b08-a1a1-46ce-a5f8-feddc43771b8/"
    }
  }

**More Information**

For more information, see `Stacks`_ in the *AWS OpsWorks User Guide*.

.. _`Stacks`: http://docs.aws.amazon.com/opsworks/latest/userguide/workingstacks.html



======
Output
======

StackSummary -> (structure)

  

  A ``StackSummary`` object that contains the results.

  

  StackId -> (string)

    

    The stack ID.

    

    

  Name -> (string)

    

    The stack name.

    

    

  Arn -> (string)

    

    The stack's ARN.

    

    

  LayersCount -> (integer)

    

    The number of layers.

    

    

  AppsCount -> (integer)

    

    The number of apps.

    

    

  InstancesCount -> (structure)

    

    An ``InstancesCount`` object with the number of instances in each status.

    

    Assigning -> (integer)

      

      The number of instances in the Assigning state.

      

      

    Booting -> (integer)

      

      The number of instances with ``booting`` status.

      

      

    ConnectionLost -> (integer)

      

      The number of instances with ``connection_lost`` status.

      

      

    Deregistering -> (integer)

      

      The number of instances in the Deregistering state.

      

      

    Online -> (integer)

      

      The number of instances with ``online`` status.

      

      

    Pending -> (integer)

      

      The number of instances with ``pending`` status.

      

      

    Rebooting -> (integer)

      

      The number of instances with ``rebooting`` status.

      

      

    Registered -> (integer)

      

      The number of instances in the Registered state.

      

      

    Registering -> (integer)

      

      The number of instances in the Registering state.

      

      

    Requested -> (integer)

      

      The number of instances with ``requested`` status.

      

      

    RunningSetup -> (integer)

      

      The number of instances with ``running_setup`` status.

      

      

    SetupFailed -> (integer)

      

      The number of instances with ``setup_failed`` status.

      

      

    ShuttingDown -> (integer)

      

      The number of instances with ``shutting_down`` status.

      

      

    StartFailed -> (integer)

      

      The number of instances with ``start_failed`` status.

      

      

    Stopped -> (integer)

      

      The number of instances with ``stopped`` status.

      

      

    Stopping -> (integer)

      

      The number of instances with ``stopping`` status.

      

      

    Terminated -> (integer)

      

      The number of instances with ``terminated`` status.

      

      

    Terminating -> (integer)

      

      The number of instances with ``terminating`` status.

      

      

    Unassigning -> (integer)

      

      The number of instances in the Unassigning state.

      

      

    

  



.. _Managing User Permissions: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html
