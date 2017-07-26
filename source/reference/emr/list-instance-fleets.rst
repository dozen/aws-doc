[ :ref:`aws <cli:aws>` . :ref:`emr <cli:aws emr>` ]

.. _cli:aws emr list-instance-fleets:


********************
list-instance-fleets
********************



===========
Description
===========



Lists all available details about the instance fleets in a cluster.

 

.. note::

   

  The instance fleet configuration is available only in Amazon EMR versions 4.8.0 and later, excluding 5.0.x versions.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/elasticmapreduce-2009-03-31/ListInstanceFleets>`_


``list-instance-fleets`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``InstanceFleets``


========
Synopsis
========

::

    list-instance-fleets
  --cluster-id <value>
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cluster-id`` (string)


  The unique identifier of the cluster.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get configuration details of instance fleets in a cluster**

This example lists the details of instance fleets in the cluster specified.

Command::

  list-instance-fleets --cluster-id 'j-12ABCDEFGHI34JK'

Output::

  {
    "InstanceFleets": [
        {
            "Status": {
                "Timeline": {
                    "ReadyDateTime": 1488759094.637,
                    "CreationDateTime": 1488758719.817
                },
                "State": "RUNNING",
                "StateChangeReason": {
                    "Message": ""
                }
            },
            "ProvisionedSpotCapacity": 6,
            "Name": "CORE",
            "InstanceFleetType": "CORE",
            "LaunchSpecifications": {
                "SpotSpecification": {
                    "TimeoutDurationMinutes": 60,
                    "TimeoutAction": "TERMINATE_CLUSTER"
                }
            },
            "ProvisionedOnDemandCapacity": 2,
            "InstanceTypeSpecifications": [
                {
                    "BidPrice": "0.5",
                    "InstanceType": "m3.xlarge",
                    "WeightedCapacity": 2
                }
            ],
            "Id": "if-1ABC2DEFGHIJ3"
        },
        {
            "Status": {
                "Timeline": {
                    "ReadyDateTime": 1488759058.598,
                    "CreationDateTime": 1488758719.811
                },
                "State": "RUNNING",
                "StateChangeReason": {
                    "Message": ""
                }
            },
            "ProvisionedSpotCapacity": 0,
            "Name": "MASTER",
            "InstanceFleetType": "MASTER",
            "ProvisionedOnDemandCapacity": 1,
            "InstanceTypeSpecifications": [
                {
                    "BidPriceAsPercentageOfOnDemandPrice": 100.0,
                    "InstanceType": "m3.xlarge",
                    "WeightedCapacity": 1
                }
            ],
           "Id": "if-2ABC4DEFGHIJ4"
        }
    ]
  }


======
Output
======

InstanceFleets -> (list)

  

  The list of instance fleets for the cluster and given filters.

  

  (structure)

    

    Describes an instance fleet, which is a group of EC2 instances that host a particular node type (master, core, or task) in an Amazon EMR cluster. Instance fleets can consist of a mix of instance types and On-Demand and Spot instances, which are provisioned to meet a defined target capacity. 

     

    .. note::

       

      The instance fleet configuration is available only in Amazon EMR versions 4.8.0 and later, excluding 5.0.x versions.

       

    

    Id -> (string)

      

      The unique identifier of the instance fleet.

      

      

    Name -> (string)

      

      A friendly name for the instance fleet.

      

      

    Status -> (structure)

      

      The current status of the instance fleet. 

      

      State -> (string)

        

        A code representing the instance fleet status.

        

        

      StateChangeReason -> (structure)

        

        Provides status change reason details for the instance fleet.

        

        Code -> (string)

          

          A code corresponding to the reason the state change occurred.

          

          

        Message -> (string)

          

          An explanatory message.

          

          

        

      Timeline -> (structure)

        

        Provides historical timestamps for the instance fleet, including the time of creation, the time it became ready to run jobs, and the time of termination.

        

        CreationDateTime -> (timestamp)

          

          The time and date the instance fleet was created.

          

          

        ReadyDateTime -> (timestamp)

          

          The time and date the instance fleet was ready to run jobs.

          

          

        EndDateTime -> (timestamp)

          

          The time and date the instance fleet terminated.

          

          

        

      

    InstanceFleetType -> (string)

      

      The node type that the instance fleet hosts. Valid values are MASTER, CORE, or TASK. 

      

      

    TargetOnDemandCapacity -> (integer)

      

      The target capacity of On-Demand units for the instance fleet, which determines how many On-Demand instances to provision. When the instance fleet launches, Amazon EMR tries to provision On-Demand instances as specified by  InstanceTypeConfig . Each instance configuration has a specified ``WeightedCapacity`` . When an On-Demand instance is provisioned, the ``WeightedCapacity`` units count toward the target capacity. Amazon EMR provisions instances until the target capacity is totally fulfilled, even if this results in an overage. For example, if there are 2 units remaining to fulfill capacity, and Amazon EMR can only provision an instance with a ``WeightedCapacity`` of 5 units, the instance is provisioned, and the target capacity is exceeded by 3 units. You can use  InstanceFleet$ProvisionedOnDemandCapacity to determine the Spot capacity units that have been provisioned for the instance fleet.

       

      .. note::

         

        If not specified or set to 0, only Spot instances are provisioned for the instance fleet using ``TargetSpotCapacity`` . At least one of ``TargetSpotCapacity`` and ``TargetOnDemandCapacity`` should be greater than 0. For a master instance fleet, only one of ``TargetSpotCapacity`` and ``TargetOnDemandCapacity`` can be specified, and its value must be 1.

         

      

      

    TargetSpotCapacity -> (integer)

      

      The target capacity of Spot units for the instance fleet, which determines how many Spot instances to provision. When the instance fleet launches, Amazon EMR tries to provision Spot instances as specified by  InstanceTypeConfig . Each instance configuration has a specified ``WeightedCapacity`` . When a Spot instance is provisioned, the ``WeightedCapacity`` units count toward the target capacity. Amazon EMR provisions instances until the target capacity is totally fulfilled, even if this results in an overage. For example, if there are 2 units remaining to fulfill capacity, and Amazon EMR can only provision an instance with a ``WeightedCapacity`` of 5 units, the instance is provisioned, and the target capacity is exceeded by 3 units. You can use  InstanceFleet$ProvisionedSpotCapacity to determine the Spot capacity units that have been provisioned for the instance fleet.

       

      .. note::

         

        If not specified or set to 0, only On-Demand instances are provisioned for the instance fleet. At least one of ``TargetSpotCapacity`` and ``TargetOnDemandCapacity`` should be greater than 0. For a master instance fleet, only one of ``TargetSpotCapacity`` and ``TargetOnDemandCapacity`` can be specified, and its value must be 1.

         

      

      

    ProvisionedOnDemandCapacity -> (integer)

      

      The number of On-Demand units that have been provisioned for the instance fleet to fulfill ``TargetOnDemandCapacity`` . This provisioned capacity might be less than or greater than ``TargetOnDemandCapacity`` .

      

      

    ProvisionedSpotCapacity -> (integer)

      

      The number of Spot units that have been provisioned for this instance fleet to fulfill ``TargetSpotCapacity`` . This provisioned capacity might be less than or greater than ``TargetSpotCapacity`` .

      

      

    InstanceTypeSpecifications -> (list)

      

      The specification for the instance types that comprise an instance fleet. Up to five unique instance specifications may be defined for each instance fleet. 

      

      (structure)

        

        The configuration specification for each instance type in an instance fleet.

         

        .. note::

           

          The instance fleet configuration is available only in Amazon EMR versions 4.8.0 and later, excluding 5.0.x versions.

           

        

        InstanceType -> (string)

          

          The EC2 instance type, for example ``m3.xlarge`` .

          

          

        WeightedCapacity -> (integer)

          

          The number of units that a provisioned instance of this type provides toward fulfilling the target capacities defined in  InstanceFleetConfig . Capacity values represent performance characteristics such as vCPUs, memory, or I/O. If not specified, the default value is 1.

          

          

        BidPrice -> (string)

          

          The bid price for each EC2 Spot instance type as defined by ``InstanceType`` . Expressed in USD.

          

          

        BidPriceAsPercentageOfOnDemandPrice -> (double)

          

          The bid price, as a percentage of On-Demand price, for each EC2 Spot instance as defined by ``InstanceType`` . Expressed as a number (for example, 20 specifies 20%).

          

          

        Configurations -> (list)

          

          A configuration classification that applies when provisioning cluster instances, which can include configurations for applications and software bundled with Amazon EMR.

          

          (structure)

            

            .. note::

               

              Amazon EMR releases 4.x or later.

               

             

            An optional configuration specification to be used when provisioning cluster instances, which can include configurations for applications and software bundled with Amazon EMR. A configuration consists of a classification, properties, and optional nested configurations. A classification refers to an application-specific configuration file. Properties are the settings you want to change in that file. For more information, see `Configuring Applications <http://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-configure-apps.html>`_ .

            

            Classification -> (string)

              

              The classification within a configuration.

              

              

            Configurations -> (list)

              

              A list of additional configurations to apply within a configuration object.

              

              (structure)

                

                .. note::

                   

                  Amazon EMR releases 4.x or later.

                   

                 

                An optional configuration specification to be used when provisioning cluster instances, which can include configurations for applications and software bundled with Amazon EMR. A configuration consists of a classification, properties, and optional nested configurations. A classification refers to an application-specific configuration file. Properties are the settings you want to change in that file. For more information, see `Configuring Applications <http://docs.aws.amazon.com/emr/latest/ReleaseGuide/emr-configure-apps.html>`_ .

                

                Classification -> (string)

                  

                  The classification within a configuration.

                  

                  

                Properties -> (map)

                  

                  A set of properties specified within a configuration classification.

                  

                  key -> (string)

                    

                    

                  value -> (string)

                    

                    

                  

                

              

            Properties -> (map)

              

              A set of properties specified within a configuration classification.

              

              key -> (string)

                

                

              value -> (string)

                

                

              

            

          

        EbsBlockDevices -> (list)

          

          The configuration of Amazon Elastic Block Storage (EBS) attached to each instance as defined by ``InstanceType`` .

          

          (structure)

            

            Configuration of requested EBS block device associated with the instance group.

            

            VolumeSpecification -> (structure)

              

              EBS volume specifications such as volume type, IOPS, and size (GiB) that will be requested for the EBS volume attached to an EC2 instance in the cluster.

              

              VolumeType -> (string)

                

                The volume type. Volume types supported are gp2, io1, standard.

                

                

              Iops -> (integer)

                

                The number of I/O operations per second (IOPS) that the volume supports.

                

                

              SizeInGB -> (integer)

                

                The volume size, in gibibytes (GiB). This can be a number from 1 - 1024. If the volume type is EBS-optimized, the minimum value is 10.

                

                

              

            Device -> (string)

              

              The device name that is exposed to the instance, such as /dev/sdh.

              

              

            

          

        EbsOptimized -> (boolean)

          

          Evaluates to ``TRUE`` when the specified ``InstanceType`` is EBS-optimized.

          

          

        

      

    LaunchSpecifications -> (structure)

      

      Describes the launch specification for an instance fleet. 

      

      SpotSpecification -> (structure)

        

        The launch specification for Spot instances in the fleet, which determines the defined duration and provisioning timeout behavior.

        

        TimeoutDurationMinutes -> (integer)

          

          The spot provisioning timeout period in minutes. If Spot instances are not provisioned within this time period, the ``TimeOutAction`` is taken. Minimum value is 5 and maximum value is 1440. The timeout applies only during initial provisioning, when the cluster is first created.

          

          

        TimeoutAction -> (string)

          

          The action to take when ``TargetSpotCapacity`` has not been fulfilled when the ``TimeoutDurationMinutes`` has expired. Spot instances are not uprovisioned within the Spot provisioining timeout. Valid values are ``TERMINATE_CLUSTER`` and ``SWITCH_TO_ON_DEMAND`` . SWITCH_TO_ON_DEMAND specifies that if no Spot instances are available, On-Demand Instances should be provisioned to fulfill any remaining Spot capacity.

          

          

        BlockDurationMinutes -> (integer)

          

          The defined duration for Spot instances (also known as Spot blocks) in minutes. When specified, the Spot instance does not terminate before the defined duration expires, and defined duration pricing for Spot instances applies. Valid values are 60, 120, 180, 240, 300, or 360. The duration period starts as soon as a Spot instance receives its instance ID. At the end of the duration, Amazon EC2 marks the Spot instance for termination and provides a Spot instance termination notice, which gives the instance a two-minute warning before it terminates. 

          

          

        

      

    

  

Marker -> (string)

  

  The pagination token that indicates the next set of results to retrieve.

  

  

