[ :ref:`aws <cli:aws>` . :ref:`emr <cli:aws emr>` ]

.. _cli:aws emr add-instance-fleet:


******************
add-instance-fleet
******************



===========
Description
===========



Adds an instance fleet to a running cluster.

 

.. note::

   

  The instance fleet configuration is available only in Amazon EMR versions 4.8.0 and later, excluding 5.0.x.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticmapreduce-2009-03-31/AddInstanceFleet>`_


========
Synopsis
========

::

    add-instance-fleet
  --cluster-id <value>
  --instance-fleet <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cluster-id`` (string)


  The unique identifier of the cluster.

  

``--instance-fleet`` (structure)


  Specifies the configuration of the instance fleet.

  



JSON Syntax::

  {
    "Name": "string",
    "InstanceFleetType": "MASTER"|"CORE"|"TASK",
    "TargetOnDemandCapacity": integer,
    "TargetSpotCapacity": integer,
    "InstanceTypeConfigs": [
      {
        "InstanceType": "string",
        "WeightedCapacity": integer,
        "BidPrice": "string",
        "BidPriceAsPercentageOfOnDemandPrice": double,
        "EbsConfiguration": {
          "EbsBlockDeviceConfigs": [
            {
              "VolumeSpecification": {
                "VolumeType": "string",
                "Iops": integer,
                "SizeInGB": integer
              },
              "VolumesPerInstance": integer
            }
            ...
          ],
          "EbsOptimized": true|false
        },
        "Configurations": [
          {
            "Classification": "string",
            "Configurations": [
              {
                "Classification": "string",
                "Configurations": ,
                "Properties": {"string": "string"
                  ...}
              }
              ...
            ],
            "Properties": {"string": "string"
              ...}
          }
          ...
        ]
      }
      ...
    ],
    "LaunchSpecifications": {
      "SpotSpecification": {
        "TimeoutDurationMinutes": integer,
        "TimeoutAction": "SWITCH_TO_ON_DEMAND"|"TERMINATE_CLUSTER",
        "BlockDurationMinutes": integer
      }
    }
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To add a task instance fleet to a cluster**

This example adds a new task instance fleet to the cluster specified.

Command::

  aws emr add-instance-fleet --cluster-id 'j-12ABCDEFGHI34JK' --instance-fleet  InstanceFleetType=TASK,TargetSpotCapacity=1,LaunchSpecifications={SpotSpecification='{TimeoutDurationMinutes=20,TimeoutAction=TERMINATE_CLUSTER}'},InstanceTypeConfigs=['{InstanceType=m3.xlarge,BidPrice=0.5}']

Output::

  {
     "ClusterId": "j-12ABCDEFGHI34JK",
     "InstanceFleetId": "if-23ABCDEFGHI45JJ"
  }


======
Output
======

ClusterId -> (string)

  

  The unique identifier of the cluster.

  

  

InstanceFleetId -> (string)

  

  The unique identifier of the instance fleet.

  

  

