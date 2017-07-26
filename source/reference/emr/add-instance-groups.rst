[ :ref:`aws <cli:aws>` . :ref:`emr <cli:aws emr>` ]

.. _cli:aws emr add-instance-groups:


*******************
add-instance-groups
*******************



===========
Description
===========

Adds an instance group to a running cluster.



========
Synopsis
========

::

    add-instance-groups
  --cluster-id <value>
  --instance-groups <value> [<value>...]




=======
Options
=======

``--cluster-id`` (string)


  A unique string that identifies the cluster. This identifier is returned by ``create-cluster`` and can also be obtained from ``list-clusters`` .

  

``--instance-groups`` (list)


  A specification of the number and type of Amazon EC2 instances to create instance groups in a cluster.

  

  Each instance group takes the following parameters: ``[Name], InstanceGroupType, InstanceType, InstanceCount, [BidPrice], [EbsConfiguration]`` . [EbsConfiguration] is optional. EbsConfiguration takes the following parameters: ``EbsOptimized`` and ``EbsBlockDeviceConfigs`` . EbsBlockDeviceConfigs is an array of EBS volume specifications, which takes the following parameters : ``([VolumeType], [SizeInGB], Iops)`` and VolumesPerInstance which is the count of EBS volumes per instance with this specification.

  



JSON Syntax::

  [
    {
      "InstanceCount": integer,
      "Name": "string",
      "InstanceGroupType": "MASTER"|"CORE"|"TASK",
      "EbsConfiguration": {
        "EbsOptimized": true|false,
        "EbsBlockDeviceConfigs": [
          {
            "VolumeSpecification": {
              "Iops": integer,
              "VolumeType": "string",
              "SizeInGB": integer
            },
            "VolumesPerInstance": integer
          }
          ...
        ]
      },
      "BidPrice": "string",
      "InstanceType": "string"
    }
    ...
  ]



