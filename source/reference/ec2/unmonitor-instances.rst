[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 unmonitor-instances:


*******************
unmonitor-instances
*******************



===========
Description
===========



Disables detailed monitoring for a running instance. For more information, see `Monitoring Your Instances and Volumes <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-cloudwatch.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/UnmonitorInstances>`_


========
Synopsis
========

::

    unmonitor-instances
  --instance-ids <value>
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-ids`` (list)


  One or more instance IDs.

  



Syntax::

  "string" "string" ...



``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To disable detailed monitoring for an instance**

This example command disables detailed monitoring for the specified instance.

Command::

  aws ec2 unmonitor-instances --instance-ids i-1234567890abcdef0

Output::

  {
    "InstanceMonitorings": [
        {
            "InstanceId": "i-1234567890abcdef0",
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

  

  The monitoring information.

  

  (structure)

    

    Describes the monitoring of an instance.

    

    InstanceId -> (string)

      

      The ID of the instance.

      

      

    Monitoring -> (structure)

      

      The monitoring for the instance.

      

      State -> (string)

        

        Indicates whether detailed monitoring is enabled. Otherwise, basic monitoring is enabled.

        

        

      

    

  

