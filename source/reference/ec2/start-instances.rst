[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 start-instances:


***************
start-instances
***************



===========
Description
===========



Starts an Amazon EBS-backed AMI that you've previously stopped.

 

Instances that use Amazon EBS volumes as their root devices can be quickly stopped and started. When an instance is stopped, the compute resources are released and you are not billed for hourly instance usage. However, your root partition Amazon EBS volume remains, continues to persist your data, and you are charged for Amazon EBS volume usage. You can restart your instance at any time. Each time you transition an instance from stopped to started, Amazon EC2 charges a full instance hour, even if transitions happen multiple times within a single hour.

 

Before stopping an instance, make sure it is in a state from which it can be restarted. Stopping an instance does not preserve data stored in RAM.

 

Performing this operation on an instance that uses an instance store as its root device returns an error.

 

For more information, see `Stopping Instances`_ in the *Amazon Elastic Compute Cloud User Guide* .



========
Synopsis
========

::

    start-instances
  --instance-ids <value>
  [--additional-info <value>]
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--instance-ids`` (list)


  One or more instance IDs.

  



Syntax::

  "string" "string" ...



``--additional-info`` (string)


  Reserved.

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To start an Amazon EC2 instance**

This example starts the specified Amazon EBS-backed instance.

Command::

  aws ec2 start-instances --instance-ids i-1a2b3c4d

Output::

    {
        "StartingInstances": [
            {
                "InstanceId": "i-1a2b3c4d",
                "CurrentState": {
                    "Code": 0,
                    "Name": "pending"
                },
                "PreviousState": {
                    "Code": 80,
                    "Name": "stopped"
                }
            }
        ]
    }

For more information, see `Stop and Start Your Instance`_ in the *Amazon Elastic Compute Cloud User Guide*.

.. _`Stop and Start Your Instance`: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Stop_Start.html



======
Output
======

StartingInstances -> (list)

  

  Information about one or more started instances.

  

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

        

        

      

    

  



.. _Stopping Instances: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Stop_Start.html
