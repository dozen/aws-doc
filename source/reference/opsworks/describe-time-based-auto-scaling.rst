[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks describe-time-based-auto-scaling:


********************************
describe-time-based-auto-scaling
********************************



===========
Description
===========



Describes time-based auto scaling configurations for specified instances.

 

.. note::

   

  You must specify at least one of the parameters.

   

 

 **Required Permissions** : To use this action, an IAM user must have a Show, Deploy, or Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions <http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworks-2013-02-18/DescribeTimeBasedAutoScaling>`_


========
Synopsis
========

::

    describe-time-based-auto-scaling
  --instance-ids <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-ids`` (list)


  An array of instance IDs.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

TimeBasedAutoScalingConfigurations -> (list)

  

  An array of ``TimeBasedAutoScalingConfiguration`` objects that describe the configuration for the specified instances.

  

  (structure)

    

    Describes an instance's time-based auto scaling configuration.

    

    InstanceId -> (string)

      

      The instance ID.

      

      

    AutoScalingSchedule -> (structure)

      

      A ``WeeklyAutoScalingSchedule`` object with the instance schedule.

      

      Monday -> (map)

        

        The schedule for Monday.

        

        key -> (string)

          

          

        value -> (string)

          

          

        

      Tuesday -> (map)

        

        The schedule for Tuesday.

        

        key -> (string)

          

          

        value -> (string)

          

          

        

      Wednesday -> (map)

        

        The schedule for Wednesday.

        

        key -> (string)

          

          

        value -> (string)

          

          

        

      Thursday -> (map)

        

        The schedule for Thursday.

        

        key -> (string)

          

          

        value -> (string)

          

          

        

      Friday -> (map)

        

        The schedule for Friday.

        

        key -> (string)

          

          

        value -> (string)

          

          

        

      Saturday -> (map)

        

        The schedule for Saturday.

        

        key -> (string)

          

          

        value -> (string)

          

          

        

      Sunday -> (map)

        

        The schedule for Sunday.

        

        key -> (string)

          

          

        value -> (string)

          

          

        

      

    

  

