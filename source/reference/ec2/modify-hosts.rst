[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 modify-hosts:


************
modify-hosts
************



===========
Description
===========



Modify the auto-placement setting of a Dedicated host. When auto-placement is enabled, AWS will place instances that you launch with a tenancy of ``host`` , but without targeting a specific host ID, onto any available Dedicated host in your account which has auto-placement enabled. When auto-placement is disabled, you need to provide a host ID if you want the instance to launch onto a specific host. If no host ID is provided, the instance will be launched onto a suitable host which has auto-placement enabled.



========
Synopsis
========

::

    modify-hosts
  --host-ids <value>
  --auto-placement <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--host-ids`` (list)


  The host IDs of the Dedicated hosts you want to modify.

  



Syntax::

  "string" "string" ...



``--auto-placement`` (string)


  Specify whether to enable or disable auto-placement.

  

  Possible values:

  
  *   ``on``

  
  *   ``off``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe Dedicated hosts in your account and generate a machine-readable list**

To output a list of Dedicated host IDs in JSON (comma separated).

Command::

  aws ec2 describe-hosts --query 'Hosts[].HostId' --output json

Output::

  [
  "h-085664df5899941c",
  "h-056c1b0724170dc38"
  ]

To output a list of Dedicated host IDs in plaintext (comma separated).

Command::

  aws ec2 describe-hosts --query 'Hosts[].HostId' --output text

Output::
h-085664df5899941c
h-056c1b0724170dc38

**To describe available Dedicated hosts in your account**

Command::

  aws ec2 describe-hosts --filter "Name=state,Values=available"

Output::

  { 
    "Hosts":  [
        {
            "HostId": "h-085664df5899941c"
            "HostProperties: {
                "Cores": 20,
                 "Sockets": 2,
                  "InstanceType": "m3.medium".
                  "TotalVCpus": 32
             },
             "Instances": [],
              "State": "available",
              "AvailabilityZone": "us-east-1b",
              "AvailableCapacity": {
                  "AvailableInstanceCapacity": [
                      {
                            "AvailableCapacity": 32,
                            "InstanceType": "m3.medium",
                            "TotalCapacity": 32
                      }
                   ],
                   "AvailableVCpus": 32
              },
              "AutoPlacement": "off"
       }
    ]
  }
  


======
Output
======

Successful -> (list)

  

  The IDs of the Dedicated hosts that were successfully modified.

  

  (string)

    

    

  

Unsuccessful -> (list)

  

  The IDs of the Dedicated hosts that could not be modified. Check whether the setting you requested can be used.

  

  (structure)

    

    Information about items that were not successfully processed in a batch call.

    

    Error -> (structure)

      

      Information about the error.

      

      Code -> (string)

        

        The error code.

        

        

      Message -> (string)

        

        The error message accompanying the error code.

        

        

      

    ResourceId -> (string)

      

      The ID of the resource.

      

      

    

  

