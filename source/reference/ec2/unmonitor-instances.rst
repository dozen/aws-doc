[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 unmonitor-instances:


*******************
unmonitor-instances
*******************



===========
Description
===========



Disables monitoring for a running instance. For more information about monitoring instances, see `Monitoring Your Instances and Volumes`_ in the *Amazon Elastic Compute Cloud User Guide* .



========
Synopsis
========

::

    unmonitor-instances
  [--dry-run | --no-dry-run]
  --instance-ids <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--instance-ids`` (list)


  One or more instance IDs.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To disable detailed monitoring for an instance**

This example command disables detailed monitoring for the specified instance.

Command::

  aws ec2 unmonitor-instances --instance-ids i-570e5a28

Output::

  {
    "InstanceMonitorings": [
        {
            "InstanceId": "i-570e5a28",
            "Monitoring": {
                "State": "disabling"
            }
        }
    ]
  }


======
Output
======

InstanceMonitorings -> (list)

  

  Monitoring information for one or more instances.

  

  (structure)

    

    Describes the monitoring information of the instance.

    

    InstanceId -> (string)

      

      The ID of the instance.

      

      

    Monitoring -> (structure)

      

      The monitoring information.

      

      State -> (string)

        

        Indicates whether monitoring is enabled for the instance.

        

        

      

    

  



.. _Monitoring Your Instances and Volumes: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-cloudwatch.html
