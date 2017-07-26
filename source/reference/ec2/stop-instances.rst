[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 stop-instances:


**************
stop-instances
**************



===========
Description
===========



Stops an Amazon EBS-backed instance. Each time you transition an instance from stopped to started, Amazon EC2 charges a full instance hour, even if transitions happen multiple times within a single hour.

 

You can't start or stop Spot instances.

 

Instances that use Amazon EBS volumes as their root devices can be quickly stopped and started. When an instance is stopped, the compute resources are released and you are not billed for hourly instance usage. However, your root partition Amazon EBS volume remains, continues to persist your data, and you are charged for Amazon EBS volume usage. You can restart your instance at any time.

 

Before stopping an instance, make sure it is in a state from which it can be restarted. Stopping an instance does not preserve data stored in RAM.

 

Performing this operation on an instance that uses an instance store as its root device returns an error.

 

You can stop, start, and terminate EBS-backed instances. You can only terminate instance store-backed instances. What happens to an instance differs if you stop it or terminate it. For example, when you stop an instance, the root device and any other devices attached to the instance persist. When you terminate an instance, the root device and any other devices attached during the instance launch are automatically deleted. For more information about the differences between stopping and terminating instances, see `Instance Lifecycle`_ in the *Amazon Elastic Compute Cloud User Guide* .

 

For more information about troubleshooting, see `Troubleshooting Stopping Your Instance`_ in the *Amazon Elastic Compute Cloud User Guide* .



========
Synopsis
========

::

    stop-instances
  [--dry-run | --no-dry-run]
  --instance-ids <value>
  [--force | --no-force]
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



``--force`` | ``--no-force`` (boolean)


  Forces the instances to stop. The instances do not have an opportunity to flush file system caches or file system metadata. If you use this option, you must perform file system check and repair procedures. This option is not recommended for Windows instances.

   

  Default: ``false`` 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To stop an Amazon EC2 instance**

This example stops the specified Amazon EBS-backed instance.

Command::

  aws ec2 stop-instances --instance-ids i-1a2b3c4d

Output::

    {
        "StoppingInstances": [
            {
                "InstanceId": "i-1a2b3c4d",
                "CurrentState": {
                    "Code": 64,
                    "Name": "stopping"
                },
                "PreviousState": {
                    "Code": 16,
                    "Name": "running"
                }
            }
        ]
    }

For more information, see `Stop and Start Your Instance`_ in the *Amazon Elastic Compute Cloud User Guide*.

.. _`Stop and Start Your Instance`: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Stop_Start.html



======
Output
======

StoppingInstances -> (list)

  

  Information about one or more stopped instances.

  

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
.. _Troubleshooting Stopping Your Instance: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/TroubleshootingInstancesStopping.html
