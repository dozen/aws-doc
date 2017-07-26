[ :ref:`aws <cli:aws>` . :ref:`emr <cli:aws emr>` ]

.. _cli:aws emr create-cluster:


**************
create-cluster
**************



===========
Description
===========

Creates an Amazon EMR cluster with specified software.

Quick start:

aws emr create-cluster --release-label <release-label> --instance-type <instance-type> [--instance-count <instance-count>]

Values for variables Instance Profile (under EC2 Attributes), Service Role, Log URI, and Key Name (under EC2 Attributes) can be set in the AWS CLI config file using the "aws configure set" command.




========
Synopsis
========

::

      create-cluster
     --release-label <value>   | --ami-version <value>
     --instance-fleets <value> | --instance-groups <value> | --instance-type <value> --instance-count <value>  
     [--auto-terminate | --no-auto-terminate]
     [--use-default-roles]
     [--service-role <value>]
     [--configurations <value>]
     [--name <value>]
     [--log-uri <value>]
     [--additional-info <value>]
     [--ec2-attributes <value>]
     [--termination-protected | --no-termination-protected]
     [--visible-to-all-users | --no-visible-to-all-users]
     [--enable-debugging | --no-enable-debugging]
     [--tags <value>]
     [--applications <value>]
     [--emrfs <value>]
     [--bootstrap-actions <value>]
     [--steps <value>]
     [--restore-from-hbase-backup <value>]
     [--security-configuration <value>]
     [--custom-ami-id <value>]
     [--ebs-root-volume-size <value>]
     [--repo-upgrade-on-boot <value>]





=======
Options
=======

``--release-label`` (string)


  The identifier for the EMR release, which includes a set of software, to use with Amazon EC2 instances that are part of an Amazon EMR cluster. For example, --release-label emr-4.0.0 You cannot specify both a release label (emr-4.0.0 and later) and AMI version (3.x or 2.x) on a cluster.

  

  For details about the releases available in Amazon Elastic MapReduce, go to Releases Available in Amazon Elastic MapReduce in the Amazon Elastic MapReduce Documentation.

  

  http://docs.aws.amazon.com/ElasticMapReduce/latest/Applications/emr-release.html

  

  Please use ami-version if you want to specify AMI Versions for your Amazon EMR cluster (3.x and 2.x)

  

``--ami-version`` (string)


  The version number of the Amazon Machine Image (AMI) to use for Amazon EC2 instances in the cluster. For example,--ami-version 3.1.0 You cannot specify both a release label (emr-4.0.0 and later) and an AMI version (3.x or 2.x) on a cluster

  

  For details about the AMIs currently supported by Amazon Elastic MapReduce, go to AMI Versions Supported in Amazon Elastic MapReduce in the Amazon Elastic MapReduce Developer's Guide.

  

  http://docs.aws.amazon.com/ElasticMapReduce/latest/DeveloperGuide/ami-versions-supported.html

  

``--instance-groups`` (list)


  A specification of the number and type of Amazon EC2 instances to create instance groups in a cluster.

  

  Each instance group takes the following parameters: ``[Name], InstanceGroupType, InstanceType, InstanceCount, [BidPrice], [EbsConfiguration], [AutoScalingPolicy]`` . [EbsConfiguration] and [AutoScalingPolicy] are optional. EbsConfiguration takes the following parameters: ``EbsOptimized`` and ``EbsBlockDeviceConfigs`` . EbsBlockDeviceConfigs is an array of EBS volume specifications, which takes the following parameters : ``([VolumeType], [SizeInGB], Iops)`` and VolumesPerInstance which is the count of EBS volumes per instance with this specification.

  

  AutoScalingPolicy takes the following parameters: ``Constraints`` and ``Rules`` . Constraints takes the following parameters: ``MinCapacity, MaxCapacity`` . Rules is a list of AutoScaling rules associated to the policy. Each rule has the following parameters: ``Name, [Description], Action, Trigger`` . Action takes the following parameters: ``Market, SimpleScalingPolicyConfiguration (AdjustmentType, ScalingAdjustment)`` . Trigger takes ``CloudWatchAlarmDefinition(AlarmNamePrefix, ComparisonOperator, EvaluationPeriods, MetricName, Namespace, Period, Statistic, Threshold, Unit, [Dimensions])`` .

  



JSON Syntax::

  [
    {
      "InstanceCount": integer,
      "Name": "string",
      "InstanceGroupType": "MASTER"|"CORE"|"TASK",
      "AutoScalingPolicy": {
        "Rules": [
          {
            "Action": {
              "SimpleScalingPolicyConfiguration": {
                "ScalingAdjustment": integer,
                "CoolDown": integer,
                "AdjustmentType": "CHANGE_IN_CAPACITY"|"PERCENT_CHANGE_IN_CAPACITY"|"EXACT_CAPACITY"
              },
              "Market": "ON_DEMAND"|"SPOT"
            },
            "Trigger": {
              "CloudWatchAlarmDefinition": {
                "EvaluationPeriods": integer,
                "Dimensions": [
                  {
                    "Key": "string",
                    "Value": "string"
                  }
                  ...
                ],
                "Namespace": "string",
                "Period": integer,
                "ComparisonOperator": "string",
                "Statistic": "string",
                "Threshold": double,
                "Unit": "string",
                "MetricName": "string"
              }
            },
            "Name": "string",
            "Description": "string"
          }
          ...
        ],
        "Constraints": {
          "MinCapacity": integer,
          "MaxCapacity": integer
        }
      },
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



``--instance-type`` (string)


  Shortcut option for --instance-groups. A specification of the type of Amazon EC2 instances used together with --instance-count (optional) to create instance groups in a cluster. Specifying the --instance-type argument without also specifying --instance-count launches a single-node cluster.

  

``--instance-count`` (string)


  Shortcut option for --instance-groups. A specification of the number of Amazon EC2 instances used together with --instance-type to create instance groups in a cluster. EMR will use one node as the cluster's master node and use the remainder of the nodes as core nodes. Specifying the --instance-type argument without also specifying --instance-count launches a single-node cluster.

  

``--auto-terminate`` | ``--no-auto-terminate`` (boolean)


  Specifies whether the cluster should terminate after completing all the steps. Auto termination is off by default.

  

``--instance-fleets`` (list)


  A specification of the number and type of Amazon EC2 instances used to create instance fleets in a cluster.

  

  Each instance fleet takes the following parameters: ``[Name], InstanceFleetType, InstanceTypeConfigs, TargetOnDemandCapacity or TargetSpotCapacity, [BidPrice], [EbsConfiguration]`` . [EbsConfiguration] is optional. EbsConfiguration takes the following parameters: ``EbsOptimized`` and ``EbsBlockDeviceConfigs`` . EbsBlockDeviceConfigs is an array of EBS volume specifications, which takes the following parameters : ``([VolumeType], [SizeInGB], Iops)`` and VolumesPerInstance. VolumesPerInstance is the count of EBS volumes per instance with this specification.

  



JSON Syntax::

  [
    {
      "Name": "string",
      "InstanceFleetType": "MASTER"|"CORE"|"TASK",
      "LaunchSpecifications": {
        "SpotSpecification": {
          "TimeoutDurationMinutes": integer,
          "BlockDurationMinutes": integer,
          "TimeoutAction": "TERMINATE_CLUSTER"|"SWITCH_TO_ONDEMAND"
        }
      },
      "TargetSpotCapacity": integer,
      "InstanceTypeConfigs": [
        {
          "WeightedCapacity": integer,
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
          "BidPriceAsPercentageOfOnDemandPrice": double,
          "InstanceType": "string",
          "Configurations": "string"
        }
        ...
      ],
      "TargetOnDemandCapacity": integer
    }
    ...
  ]



``--name`` (string)


  The name of the cluster. The default is "Development Cluster".

  

``--log-uri`` (string)


  The location in Amazon S3 to write the log files of the cluster. If a value is not provided, logs are not created.

  

``--service-role`` (string)


``--auto-scaling-role`` (string)


``--use-default-roles`` (boolean)


``--configurations`` (string)


``--ec2-attributes`` (structure)




Shorthand Syntax::

    ServiceAccessSecurityGroup=string,AvailabilityZone=string,AdditionalSlaveSecurityGroups=string,string,EmrManagedMasterSecurityGroup=string,SubnetIds=string,string,KeyName=string,InstanceProfile=string,SubnetId=string,AdditionalMasterSecurityGroups=string,string,AvailabilityZones=string,string,EmrManagedSlaveSecurityGroup=string




JSON Syntax::

  {
    "ServiceAccessSecurityGroup": "string",
    "AvailabilityZone": "string",
    "AdditionalSlaveSecurityGroups": ["string", ...],
    "EmrManagedMasterSecurityGroup": "string",
    "SubnetIds": ["string", ...],
    "KeyName": "string",
    "InstanceProfile": "string",
    "SubnetId": "string",
    "AdditionalMasterSecurityGroups": ["string", ...],
    "AvailabilityZones": ["string", ...],
    "EmrManagedSlaveSecurityGroup": "string"
  }



``--termination-protected`` | ``--no-termination-protected`` (boolean)


``--scale-down-behavior`` (string)


``--visible-to-all-users`` | ``--no-visible-to-all-users`` (boolean)


``--enable-debugging`` | ``--no-enable-debugging`` (boolean)


``--tags`` (list)




Syntax::

  "string" "string" ...



``--bootstrap-actions`` (list)




Shorthand Syntax::

    Path=string,Args=string,string,Name=string ...




JSON Syntax::

  [
    {
      "Path": "string",
      "Args": ["string", ...],
      "Name": "string"
    }
    ...
  ]



``--applications`` (list)




Shorthand Syntax::

    Args=string,string,Name=string ...




JSON Syntax::

  [
    {
      "Args": ["string", ...],
      "Name": "MapR"|"HUE"|"HIVE"|"PIG"|"HBASE"|"IMPALA"|"GANGLIA"|"HADOOP"|"SPARK"
    }
    ...
  ]



``--emrfs`` (structure)




Shorthand Syntax::

    Args=string,string,Encryption=string,Consistent=boolean,ProviderType=string,KMSKeyId=string,CustomProviderLocation=string,SSE=boolean,RetryCount=integer,RetryPeriod=integer,CustomProviderClass=string




JSON Syntax::

  {
    "Args": ["string", ...],
    "Encryption": "SERVERSIDE"|"CLIENTSIDE",
    "Consistent": true|false,
    "ProviderType": "KMS"|"CUSTOM",
    "KMSKeyId": "string",
    "CustomProviderLocation": "string",
    "SSE": true|false,
    "RetryCount": integer,
    "RetryPeriod": integer,
    "CustomProviderClass": "string"
  }



``--steps`` (list)




Shorthand Syntax::

    Name=string,Args=string,string,Jar=string,ActionOnFailure=string,MainClass=string,Type=string,Properties=string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Args": ["string", ...],
      "Jar": "string",
      "ActionOnFailure": "TERMINATE_CLUSTER"|"CANCEL_AND_WAIT"|"CONTINUE",
      "MainClass": "string",
      "Type": "CUSTOM_JAR"|"STREAMING"|"HIVE"|"PIG"|"IMPALA",
      "Properties": "string"
    }
    ...
  ]



``--additional-info`` (string)


``--restore-from-hbase-backup`` (structure)




Shorthand Syntax::

    BackupVersion=string,Dir=string




JSON Syntax::

  {
    "BackupVersion": "string",
    "Dir": "string"
  }



``--security-configuration`` (string)


``--custom-ami-id`` (string)


``--ebs-root-volume-size`` (string)


``--repo-upgrade-on-boot`` (string)




========
Examples
========

Note: some of these examples assume that you have specified your Amazon EMR service role and Amazon EC2 instance profile in the AWS CLI configuration file. If you have not done this, you must specify each required IAM role or use the --use-default-roles parameter when creating your cluster. You can learn more about specifying parameter values for Amazon EMR commands here:
http://docs.aws.amazon.com/ElasticMapReduce/latest/DeveloperGuide/emr-aws-cli-config.html

**1. Quick start: to create an Amazon EMR cluster**

- Command::

    aws emr create-cluster --release-label emr-5.3.1  --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge --auto-terminate

**2. Create an Amazon EMR cluster with default ServiceRole and InstanceProfile roles**

- Create an Amazon EMR cluster that uses the --instance-groups configuration::

  aws emr create-cluster --release-label emr-5.3.1  --service-role EMR_DefaultRole --ec2-attributes InstanceProfile=EMR_EC2_DefaultRole --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge

- Create an Amazon EMR cluster that uses the --instance-fleets configuration, specifying two instance types for each fleet and two EC2 Subnets::

  aws emr create-cluster --release-label emr-5.3.1 --service-role EMR_DefaultRole --ec2-attributes InstanceProfile=EMR_EC2_DefaultRole,SubnetIds=['subnet-ab12345c','subnet-de67890f'] --instance-fleets InstanceFleetType=MASTER,TargetOnDemandCapacity=1,InstanceTypeConfigs=['{InstanceType=m3.xlarge}'] InstanceFleetType=CORE,TargetSpotCapacity=11,InstanceTypeConfigs=['{InstanceType=m3.xlarge,BidPrice=0.5,WeightedCapacity=3}','{InstanceType=m4.2xlarge,BidPrice=0.9,WeightedCapacity=5}'],LaunchSpecifications={SpotSpecification='{TimeoutDurationMinutes=120,TimeoutAction=SWITCH_TO_ON_DEMAND}'}

**3. Create an Amazon EMR cluster with default roles**

- Command::

    aws emr create-cluster --release-label emr-5.3.1  --use-default-roles --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge --auto-terminate

**4. Create an Amazon EMR cluster with applications**

- Create an Amazon EMR cluster with Hadoop, Hive and Pig installed::

  aws emr create-cluster --applications Name=Hadoop Name=Hive Name=Pig --release-label emr-5.3.1  --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge --auto-terminate

- Create an Amazon EMR cluster with Spark installed:

	 aws emr create-cluster --release-label emr-5.3.1 --applications Name=Spark --ec2-attributes KeyName=myKey --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge --auto-terminate

**5. Change configuration for Hadoop MapReduce**

The following example changes the maximum number of map tasks and sets the NameNode heap size:

- Specifying configurations from a local file::

    aws emr create-cluster --configurations file://configurations.json --release-label emr-5.3.1 --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge --auto-terminate

- Specifying configurations from a file in Amazon S3::

    aws emr create-cluster --configurations https://s3.amazonaws.com/myBucket/configurations.json --release-label emr-5.3.1 --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge --auto-terminate

- Contents of configurations.json::

    [
     {
       "Classification": "mapred-site",
       "Properties": {
           "mapred.tasktracker.map.tasks.maximum": 2
       }
     },
     {
       "Classification": "hadoop-env",
       "Properties": {},
       "Configurations": [
           {
             "Classification": "export",
             "Properties": {
                 "HADOOP_DATANODE_HEAPSIZE": 2048,
                 "HADOOP_NAMENODE_OPTS": "-XX:GCTimeRatio=19"
             }
           }
       ]
     }
    ]

**6. Create an Amazon EMR cluster with MASTER, CORE, and TASK instance groups**

- Command::

    aws emr create-cluster --release-label emr-5.3.1  --auto-terminate --instance-groups Name=Master,InstanceGroupType=MASTER,InstanceType=m3.xlarge,InstanceCount=1 Name=Core,InstanceGroupType=CORE,InstanceType=m3.xlarge,InstanceCount=2 Name=Task,InstanceGroupType=TASK,InstanceType=m3.xlarge,InstanceCount=2

**7. Specify whether the cluster should terminate after completing all the steps**

- Create an Amazon EMR cluster that terminates after completing all the steps::

    aws emr create-cluster --release-label emr-5.3.1   --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge  InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge --auto-terminate

**8. Specify EC2 Attributes**

- Create an Amazon EMR cluster with the Amazon EC2 key pair "myKey" and instance profile "myProfile"::

    aws emr create-cluster --ec2-attributes KeyName=myKey,InstanceProfile=myProfile --release-label emr-5.3.1   --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge --auto-terminate

- Create an Amazon EMR cluster in an Amazon VPC subnet::

    aws emr create-cluster --ec2-attributes SubnetId=subnet-xxxxx --release-label emr-5.3.1   --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge --auto-terminate

- Create an Amazon EMR cluster in an Availability Zone. For example, us-east-1b::

    aws emr create-cluster --ec2-attributes AvailabilityZone=us-east-1b --release-label emr-5.3.1  --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge

- Create an Amazon EMR cluster specifying the Amazon EC2 security groups::

	aws emr create-cluster --release-label emr-5.3.1 --service-role myServiceRole --ec2-attributes InstanceProfile=myRole,EmrManagedMasterSecurityGroup=sg-master1,EmrManagedSlaveSecurityGroup=sg-slave1,AdditionalMasterSecurityGroups=[sg-addMaster1,sg-addMaster2,sg-addMaster3,sg-addMaster4],AdditionalSlaveSecurityGroups=[sg-addSlave1,sg-addSlave2,sg-addSlave3,sg-addSlave4] --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge

- Create an Amazon EMR cluster specifying only the Amazon EMR-managed Amazon EC2 security groups::

	aws emr create-cluster --release-label emr-5.3.1 --service-role myServiceRole --ec2-attributes InstanceProfile=myRole,EmrManagedMasterSecurityGroup=sg-master1,EmrManagedSlaveSecurityGroup=sg-slave1 --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge

- Create an Amazon EMR cluster specifying only the additional Amazon EC2 security groups::

    aws emr create-cluster --release-label emr-5.3.1 --service-role myServiceRole --ec2-attributes InstanceProfile=myRole,AdditionalMasterSecurityGroups=[sg-addMaster1,sg-addMaster2,sg-addMaster3,sg-addMaster4],AdditionalSlaveSecurityGroups=[sg-addSlave1,sg-addSlave2,sg-addSlave3,sg-addSlave4] --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge

- Create an Amazon EMR cluster in a VPC private subnet and use a specific Amazon EC2 security group to enable the Amazon EMR service access (required for clusters in private subnets)::

    aws  emr create-cluster --release-label emr-5.3.1 --service-role myServiceRole --ec2-attributes InstanceProfile=myRole,ServiceAccessSecurityGroup=sg-service-access,EmrManagedMasterSecurityGroup=sg-master,EmrManagedSlaveSecurityGroup=sg-slave --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge


- JSON equivalent (contents of ec2_attributes.json)::

    [
     {
       "SubnetId": "subnet-xxxxx",
       "KeyName": "myKey",
       "InstanceProfile":"myRole",
       "EmrManagedMasterSecurityGroup": "sg-master1",
       "EmrManagedSlaveSecurityGroup": "sg-slave1",
       "ServiceAccessSecurityGroup": "sg-service-access"
       "AdditionalMasterSecurityGroups": ["sg-addMaster1","sg-addMaster2","sg-addMaster3","sg-addMaster4"],
       "AdditionalSlaveSecurityGroups": ["sg-addSlave1","sg-addSlave2","sg-addSlave3","sg-addSlave4"]
     }
   ]

NOTE: JSON arguments must include options and values as their own items in the list.

- Command (using ec2_attributes.json)::

	aws emr create-cluster --release-label emr-5.3.1 --service-role myServiceRole --ec2-attributes file://./ec2_attributes.json  --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge

**9. Enable debugging and specify a Log URI**

- Command::

    aws emr create-cluster --enable-debugging --log-uri s3://myBucket/myLog  --release-label emr-5.3.1  --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge --auto-terminate

**10. Add tags when creating an Amazon EMR cluster**

- Add a list of tags::

    aws emr create-cluster --tags name="John Doe" age=29 address="123 East NW Seattle" --release-label emr-5.3.1  --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge --auto-terminate

- List tags of an Amazon EMR cluster::

    aws emr describe-cluster --cluster-id j-XXXXXXYY --query Cluster.Tags

**11. Use a security configuration to enable encryption**

- Command::

    aws emr create-cluster --instance-type m3.xlarge --release-label emr-5.3.1 --security-configuration mySecurityConfiguration

**12. To create an Amazon EMR cluster with EBS volumes configured to the instance groups**

- Create a cluster with multiple EBS volumes attached to the CORE instance group. EBS volumes can be attached to MASTER, CORE, and TASK instance groups. For instance groups with EBS configurations, which have an embedded JSON structure, you should enclose the entire instance group argument with single quotes. For instance groups with no EBS configuration, using single quotes is optional.

- Command::

    aws emr create-cluster --release-label emr-5.3.1  --use-default-roles --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=d2.xlarge 'InstanceGroupType=CORE,InstanceCount=2,InstanceType=d2.xlarge,EbsConfiguration={EbsOptimized=true,EbsBlockDeviceConfigs=[{VolumeSpecification={VolumeType=gp2,SizeInGB=100}},{VolumeSpecification={VolumeType=io1,SizeInGB=100,Iops=100},VolumesPerInstance=4}]}' --auto-terminate

- Create a cluster with multiple EBS volumes attached to the MASTER instance group.

- Command::

    aws emr create-cluster --release-label emr-5.3.1 --use-default-roles --instance-groups 'InstanceGroupType=MASTER, InstanceCount=1, InstanceType=d2.xlarge, EbsConfiguration={EbsOptimized=true, EbsBlockDeviceConfigs=[{VolumeSpecification={VolumeType=io1, SizeInGB=100, Iops=100}},{VolumeSpecification={VolumeType=standard,SizeInGB=50},VolumesPerInstance=3}]}' InstanceGroupType=CORE,InstanceCount=2,InstanceType=d2.xlarge --auto-terminate

- Required parameters::

    VolumeType, SizeInGB if EbsBlockDeviceConfigs specified

- Create a cluster with an Auto Scaling policy attached to the CORE instance group. The Auto Scaling policy can be attached to CORE and TASK instance groups. For instance groups with an Auto Scaling policy attached, you should enclose the entire instance group argument with single quotes. For instance groups with no Auto Scaling policy, using single quotes is optional.

- Command::

    aws emr create-cluster --release-label emr-5.3.1 --use-default-roles --auto-scaling-role EMR_AutoScaling_DefaultRole --instance-groups InstanceGroupType=MASTER,InstanceType=d2.xlarge,InstanceCount=1 'InstanceGroupType=CORE,InstanceType=d2.xlarge,InstanceCount=2,AutoScalingPolicy={Constraints={MinCapacity=1,MaxCapacity=5},Rules=[{Name=TestRule,Description=TestDescription,Action={Market=ON_DEMAND,SimpleScalingPolicyConfiguration={AdjustmentType=EXACT_CAPACITY,ScalingAdjustment=2}},Trigger={CloudWatchAlarmDefinition={ComparisonOperator=GREATER_THAN,EvaluationPeriods=5,MetricName=TestMetric,Namespace=EMR,Period=3,Statistic=MAXIMUM,Threshold=4.5,Unit=NONE,Dimensions=[{Key=TestKey,Value=TestValue}]}}}]}'

**13. To add custom JAR steps to a cluster when creating an Amazon EMR cluster**

- Command::

    aws emr create-cluster --steps Type=CUSTOM_JAR,Name=CustomJAR,ActionOnFailure=CONTINUE,Jar=s3://myBucket/mytest.jar,Args=arg1,arg2,arg3 Type=CUSTOM_JAR,Name=CustomJAR,ActionOnFailure=CONTINUE,Jar=s3://myBucket/mytest.jar,MainClass=mymainclass,Args=arg1,arg2,arg3  --release-label emr-5.3.1  --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge --auto-terminate

- Custom JAR steps required parameters::

    Jar

- Custom JAR steps optional parameters::

    Type, Name, ActionOnFailure, Args

**14. To add streaming steps when creating an Amazon EMR cluster**

- Command::

    aws emr create-cluster --steps Type=STREAMING,Name='Streaming Program',ActionOnFailure=CONTINUE,Args=[-files,s3://elasticmapreduce/samples/wordcount/wordSplitter.py,-mapper,wordSplitter.py,-reducer,aggregate,-input,s3://elasticmapreduce/samples/wordcount/input,-output,s3://mybucket/wordcount/output] --release-label emr-5.3.1  --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge --auto-terminate

- Streaming steps required parameters::

    Type, Args

- Streaming steps optional parameters::

    Name, ActionOnFailure

- JSON equivalent (contents of step.json)::

    [
     {
       "Name": "JSON Streaming Step",
       "Args": ["-files","s3://elasticmapreduce/samples/wordcount/wordSplitter.py","-mapper","wordSplitter.py","-reducer","aggregate","-input","s3://elasticmapreduce/samples/wordcount/input","-output","s3://mybucket/wordcount/output"],
       "ActionOnFailure": "CONTINUE",
       "Type": "STREAMING"
     }
   ]

NOTE: JSON arguments must include options and values as their own items in the list.

- Command (using step.json)::

    aws emr create-cluster --steps file://./step.json --release-label emr-4.0.0  --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge --auto-terminate

**15. To use multiple files in a streaming step (JSON only)**

- JSON (multiplefiles.json)::

   [
     {
        "Name": "JSON Streaming Step",
        "Type": "STREAMING",
        "ActionOnFailure": "CONTINUE",
        "Args": [
            "-files",
            "s3://mybucket/mapper.py,s3://mybucket/reducer.py",
            "-mapper",
            "mapper.py",
            "-reducer",
            "reducer.py",
            "-input",
            "s3://mybucket/input",
            "-output",
            "s3://mybucket/output"]
     }
   ]

- Command::

    aws emr create-cluster --steps file://./multiplefiles.json --release-label emr-5.3.1 --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge --auto-terminate

**16. To add Hive steps when creating an Amazon EMR cluster**

- Command::

    aws emr create-cluster --steps Type=HIVE,Name='Hive program',ActionOnFailure=CONTINUE,ActionOnFailure=TERMINATE_CLUSTER,Args=[-f,s3://elasticmapreduce/samples/hive-ads/libs/model-build.q,-d,INPUT=s3://elasticmapreduce/samples/hive-ads/tables,-d,OUTPUT=s3://mybucket/hive-ads/output/2014-04-18/11-07-32,-d,LIBS=s3://elasticmapreduce/samples/hive-ads/libs] --applications Name=Hive --release-label emr-5.3.1  --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge

- Hive steps required parameters::

    Type, Args

- Hive steps optional parameters::

    Name, ActionOnFailure

**17. To add Pig steps when creating an Amazon EMR cluster**

- Command::

    aws emr create-cluster --steps Type=PIG,Name='Pig program',ActionOnFailure=CONTINUE,Args=[-f,s3://elasticmapreduce/samples/pig-apache/do-reports2.pig,-p,INPUT=s3://elasticmapreduce/samples/pig-apache/input,-p,OUTPUT=s3://mybucket/pig-apache/output] --applications Name=Pig --release-label emr-5.3.1  --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge

- Pig steps required parameters::

    Type, Args

- Pig steps optional parameters::

    Name, ActionOnFailure

**18. Add a list of bootstrap actions when creating an Amazon EMR Cluster**

- Command::

    aws emr create-cluster --bootstrap-actions Path=s3://mybucket/myscript1,Name=BootstrapAction1,Args=[arg1,arg2] Path=s3://mybucket/myscript2,Name=BootstrapAction2,Args=[arg1,arg2] --release-label emr-5.3.1  --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge --auto-terminate

**19. To enable consistent view in EMRFS and change the RetryCount and Retry Period settings when creating an Amazon EMR cluster**

- Command::

    aws emr create-cluster --instance-type m3.xlarge --release-label emr-5.3.1 --emrfs Consistent=true,RetryCount=5,RetryPeriod=30

- Required parameters::

    Consistent=true

- JSON equivalent (contents of emrfs.json)::

    {
      "Consistent": true,
      "RetryCount": 5,
      "RetryPeriod": 30
    }

- Command (Using emrfs.json)::

    aws emr create-cluster --instance-type m3.xlarge --release-label emr-5.3.1 --emrfs file://emrfs.json


**20. To enable consistent view with arguments e.g. change the DynamoDB read and write capacity when creating an Amazon EMR cluster**

- Command::

    aws emr create-cluster --instance-type m3.xlarge --release-label emr-5.3.1 --emrfs Consistent=true,RetryCount=5,RetryPeriod=30,Args=[fs.s3.consistent.metadata.read.capacity=600,fs.s3.consistent.metadata.write.capacity=300]

- Required parameters::

    Consistent=true

- JSON equivalent (contents of emrfs.json)::

    {
      "Consistent": true,
      "RetryCount": 5,
      "RetryPeriod": 30,
      "Args":["fs.s3.consistent.metadata.read.capacity=600", "fs.s3.consistent.metadata.write.capacity=300"]
    }

- Command (Using emrfs.json)::

    aws emr create-cluster --instance-type m3.xlarge --release-label emr-5.3.1 --emrfs file://emrfs.json

- Command (Using custom ami id)::

    aws emr create-cluster --instance-type m3.xlarge --release-label emr-5.3.1 --custom-ami-id ami-9be6f38c

- Command (Using custom EBS root volume)::

    aws emr create-cluster --instance-type m3.xlarge --release-label emr-5.3.1 --ebs-root-volume-size 20

- Command (Repo upgrade option on instance boot. This can be used only with custom AMIs)::

    aws emr create-cluster --instance-type m3.xlarge --release-label emr-5.3.1 --repo-upgrade-on-boot ${RepoUpgrade}

    RepoUpgrade {
       SECURITY,
       NONE
    }
