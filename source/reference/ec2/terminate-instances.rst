[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 terminate-instances:


*******************
terminate-instances
*******************



===========
Description
===========



Shuts down one or more instances. This operation is idempotent; if you terminate an instance more than once, each call succeeds.

 

Terminated instances remain visible after termination (for approximately one hour).

 

By default, Amazon EC2 deletes all EBS volumes that were attached when the instance launched. Volumes attached after instance launch continue running.

 

You can stop, start, and terminate EBS-backed instances. You can only terminate instance store-backed instances. What happens to an instance differs if you stop it or terminate it. For example, when you stop an instance, the root device and any other devices attached to the instance persist. When you terminate an instance, any attached EBS volumes with the ``DeleteOnTermination`` block device mapping parameter set to ``true`` are automatically deleted. For more information about the differences between stopping and terminating instances, see `Instance Lifecycle`_ in the *Amazon Elastic Compute Cloud User Guide* .

 

For more information about troubleshooting, see `Troubleshooting Terminating Your Instance`_ in the *Amazon Elastic Compute Cloud User Guide* .



========
Synopsis
========

::

    terminate-instances
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

**To terminate an Amazon EC2 instance**

This example terminates the specified instance.

Command::

  aws ec2 terminate-instances --instance-ids i-5203422c

Output::

  {
      "TerminatingInstances": [
          {
              "InstanceId": "i-5203422c",
              "CurrentState": {
                  "Code": 32,
                  "Name": "shutting-down"
              },
              "PreviousState": {
                  "Code": 16,
                  "Name": "running"
              }
          }
      ]
  }

For more information, see `Using Amazon EC2 Instances`_ in the *AWS Command Line Interface User Guide*.

.. _`Using Amazon EC2 Instances`: http://docs.aws.amazon.com/cli/latest/userguide/cli-ec2-launch.html



======
Output
======

TerminatingInstances -> (list)

  

  Information about one or more terminated instances.

  

  (structure)

    

    Describes an instance state change.

    

    InstanceId -> (string)

      

      The ID of the instance.

      

      

    CurrentState -> (structure)

      

      The current state of the instance.

      

      Code -> (integer)

        

        The low byte represents the state. The high byte is an opaque internal value and should be ignored.

         

         
        * ``0`` : ``pending`` 
         
        * ``16`` : ``running`` 
         
        * ``32`` : ``shutting-down`` 
         
        * ``48`` : ``terminated`` 
         
        * ``64`` : ``stopping`` 
         
        * ``80`` : ``stopped`` 
         

        

        

      Name -> (string)

        

        The current state of the instance.

        

        

      

    PreviousState -> (structure)

      

      The previous state of the instance.

      

      Code -> (integer)

        

        The low byte represents the state. The high byte is an opaque internal value and should be ignored.

         

         
        * ``0`` : ``pending`` 
         
        * ``16`` : ``running`` 
         
        * ``32`` : ``shutting-down`` 
         
        * ``48`` : ``terminated`` 
         
        * ``64`` : ``stopping`` 
         
        * ``80`` : ``stopped`` 
         

        

        

      Name -> (string)

        

        The current state of the instance.

        

        

      

    

  



.. _Instance Lifecycle: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-lifecycle.html
.. _Troubleshooting Terminating Your Instance: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/TroubleshootingInstancesShuttingDown.html
