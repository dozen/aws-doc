[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 terminate-instances:


*******************
terminate-instances
*******************



===========
Description
===========



Shuts down one or more instances. This operation is idempotent; if you terminate an instance more than once, each call succeeds. 

 

If you specify multiple instances and the request fails (for example, because of a single incorrect instance ID), none of the instances are terminated.

 

Terminated instances remain visible after termination (for approximately one hour).

 

By default, Amazon EC2 deletes all EBS volumes that were attached when the instance launched. Volumes attached after instance launch continue running.

 

You can stop, start, and terminate EBS-backed instances. You can only terminate instance store-backed instances. What happens to an instance differs if you stop it or terminate it. For example, when you stop an instance, the root device and any other devices attached to the instance persist. When you terminate an instance, any attached EBS volumes with the ``DeleteOnTermination`` block device mapping parameter set to ``true`` are automatically deleted. For more information about the differences between stopping and terminating instances, see `Instance Lifecycle <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-lifecycle.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .

 

For more information about troubleshooting, see `Troubleshooting Terminating Your Instance <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/TroubleshootingInstancesShuttingDown.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/TerminateInstances>`_


========
Synopsis
========

::

    terminate-instances
  --instance-ids <value>
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-ids`` (list)


  One or more instance IDs.

   

  Constraints: Up to 1000 instance IDs. We recommend breaking up this request into smaller batches.

  



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

**To terminate an Amazon EC2 instance**

This example terminates the specified instance.

Command::

  aws ec2 terminate-instances --instance-ids i-1234567890abcdef0

Output::

  {
      "TerminatingInstances": [
          {
              "InstanceId": "i-1234567890abcdef0",
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

        

        

      

    InstanceId -> (string)

      

      The ID of the instance.

      

      

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

        

        

      

    

  

