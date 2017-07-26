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
     --release-label <value> | --ami-version <value> 
     --instance-type <value> | --instance-groups <value>
     --instance-count <value>
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



``--instance-type`` (string)


  Shortcut option for --instance-groups. A specification of the type of Amazon EC2 instances used together with --instance-count (optional) to create instance groups in a cluster. Specifying the --instance-type argument without also specifying --instance-count launches a single-node cluster.

  

``--instance-count`` (string)


  Shortcut option for --instance-groups. A specification of the number of Amazon EC2 instances used together with --instance-type to create instance groups in a cluster. EMR will use one node as the cluster's master node and use the remainder of the nodes as core nodes. Specifying the --instance-type argument without also specifying --instance-count launches a single-node cluster.

  

``--auto-terminate`` | ``--no-auto-terminate`` (boolean)


  Specifies whether the cluster should terminate after completing all the steps. Auto termination is off by default.

  

``--name`` (string)


  The name of the cluster. The default is "Development Cluster".

  

``--log-uri`` (string)


  The location in Amazon S3 to write the log files of the cluster. If a value is not provided, logs are not created.

  

``--service-role`` (string)


``--use-default-roles`` (boolean)


``--configurations`` (string)


``--ec2-attributes`` (structure)




Shorthand Syntax::

    ServiceAccessSecurityGroup=string,AvailabilityZone=string,EmrManagedMasterSecurityGroup=string,KeyName=string,SubnetId=string,AdditionalMasterSecurityGroups=string,string,EmrManagedSlaveSecurityGroup=string,InstanceProfile=string,AdditionalSlaveSecurityGroups=string,string




JSON Syntax::

  {
    "ServiceAccessSecurityGroup": "string",
    "AvailabilityZone": "string",
    "EmrManagedMasterSecurityGroup": "string",
    "KeyName": "string",
    "SubnetId": "string",
    "AdditionalMasterSecurityGroups": ["string", ...],
    "EmrManagedSlaveSecurityGroup": "string",
    "InstanceProfile": "string",
    "AdditionalSlaveSecurityGroups": ["string", ...]
  }



``--termination-protected`` | ``--no-termination-protected`` (boolean)


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





========
Examples
========

Note: some of these examples assume you have specified your EMR service role and EC2 instance profile in the AWS CLI configuration file. If you have not done this, you must specify each required IAM role or use the --use-default-roles parameter when creating your cluster. You can learn more about specifying parameter values for EMR commands here:
http://docs.aws.amazon.com/ElasticMapReduce/latest/DeveloperGuide/emr-aws-cli-config.html

**1. Quick start: to create an Amazon EMR cluster**

- Command::

    aws emr create-cluster --release-label emr-4.0.0  --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge --auto-terminate

**2. Create an Amazon EMR cluster with ServiceRole and InstanceProfile**

- Command::

    aws emr create-cluster --release-label emr-4.0.0  --service-role EMR_DefaultRole --ec2-attributes InstanceProfile=EMR_EC2_DefaultRole --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge

**3. Create an Amazon EMR cluster with default roles**

- Command::

    aws emr create-cluster --release-label emr-4.0.0  --use-default-roles --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge --auto-terminate

**4. Create an Amazon EMR cluster with MASTER, CORE, and TASK instance groups**

- Command::

    aws emr create-cluster --release-label emr-4.0.0  --auto-terminate --instance-groups Name=Master,InstanceGroupType=MASTER,InstanceType=m3.xlarge,InstanceCount=1 Name=Core,InstanceGroupType=CORE,InstanceType=m3.xlarge,InstanceCount=2 Name=Task,InstanceGroupType=TASK,InstanceType=m3.xlarge,InstanceCount=2

**5. Specify whether the cluster should terminate after completing all the steps**

- Create an Amazon EMR cluster that will terminate after completing all the steps::

    aws emr create-cluster --release-label emr-4.0.0   --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge  InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge --auto-terminate

**6. Specify EC2 Attributes**

- Create an Amazon EMR cluster with Amazon EC2 Key Pair "myKey" and instance profile "myProfile"::

    aws emr create-cluster --ec2-attributes KeyName=myKey,InstanceProfile=myProfile --release-label emr-4.0.0   --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge --auto-terminate

- Create an Amazon EMR cluster in an Amazon VPC subnet::

    aws emr create-cluster --ec2-attributes SubnetId=subnet-xxxxx --release-label emr-4.0.0   --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge --auto-terminate

- Create an Amazon EMR cluster in an AvailabilityZone. For example, us-east-1b::

    aws emr create-cluster --ec2-attributes AvailabilityZone=us-east-1b --release-label emr-4.0.0  --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge

- Create an Amazon EMR cluster specifying the Amazon EC2 security groups::

	aws emr create-cluster --release-label emr-4.0.0 --service-role myServiceRole --ec2-attributes InstanceProfile=myRole,EmrManagedMasterSecurityGroup=sg-master1,EmrManagedSlaveSecurityGroup=sg-slave1,AdditionalMasterSecurityGroups=[sg-addMaster1,sg-addMaster2,sg-addMaster3,sg-addMaster4],AdditionalSlaveSecurityGroups=[sg-addSlave1,sg-addSlave2,sg-addSlave3,sg-addSlave4] --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge

- Create an Amazon EMR cluster specifying only the EMR managed Amazon EC2 security groups::

	aws emr create-cluster --release-label emr-4.0.0 --service-role myServiceRole --ec2-attributes InstanceProfile=myRole,EmrManagedMasterSecurityGroup=sg-master1,EmrManagedSlaveSecurityGroup=sg-slave1 --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge

- Create an Amazon EMR cluster specifying only the additional Amazon EC2 security groups::

    aws emr create-cluster --release-label emr-4.0.0 --service-role myServiceRole --ec2-attributes InstanceProfile=myRole,AdditionalMasterSecurityGroups=[sg-addMaster1,sg-addMaster2,sg-addMaster3,sg-addMaster4],AdditionalSlaveSecurityGroups=[sg-addSlave1,sg-addSlave2,sg-addSlave3,sg-addSlave4] --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge

- Create an Amazon EMR cluster in a VPC private subnet and use a specific Amazon EC2 security group to enable the Amazon EMR service access (required for clusters in private subnets)::

    aws  emr create-cluster --release-label emr-4.2.0 --service-role myServiceRole --ec2-attributes InstanceProfile=myRole,ServiceAccessSecurityGroup=sg-service-access,EmrManagedMasterSecurityGroup=sg-master,EmrManagedSlaveSecurityGroup=sg-slave --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge
 

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

	aws emr create-cluster --release-label emr-4.0.0 --service-role myServiceRole --ec2-attributes file://./ec2_attributes.json  --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge

**7. Enable debugging and specify a Log URI**

- Command::

    aws emr create-cluster --enable-debugging --log-uri s3://myBucket/myLog  --release-label emr-4.0.0  --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge --auto-terminate

**8. Add tags when creating an Amazon EMR cluster**

- Add a list of tags::

    aws emr create-cluster --tags name="John Doe" age=29 address="123 East NW Seattle" --release-label emr-4.0.0  --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge --auto-terminate

- List tags of an Amazon EMR cluster::

    aws emr describe-cluster --cluster-id j-XXXXXXYY --query Cluster.Tags

**9. Add a list of bootstrap actions when creating an Amazon EMR Cluster**

- Command::

    aws emr create-cluster --bootstrap-actions Path=s3://mybucket/myscript1,Name=BootstrapAction1,Args=[arg1,arg2] Path=s3://mybucket/myscript2,Name=BootstrapAction2,Args=[arg1,arg2] --release-label emr-4.0.0  --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge --auto-terminate

**10. Configure Hadoop MapReduce component in an EMR release**

The following example changes the maximum number of map tasks and sets the NameNode heap size:

- Specifying configurations from a local file::

    aws emr create-cluster --configurations file://configurations.json --release-label emr-4.0.0 --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge --auto-terminate

- Specifying configurations from a file in Amazon S3::
 
            aws emr create-cluster --configurations https://s3.amazonaws.com/myBucket/configurations.json --release-label emr-4.0.0 --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge --auto-terminate
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

**11. Create an Amazon EMR cluster with applications**

- Create an Amazon EMR cluster with Hadoop, Hive and Pig installed::

    aws emr create-cluster --applications Name=Hadoop Name=Hive Name=Pig --release-label emr-4.0.0  --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge --auto-terminate
 
- Create an Amazon EMR cluster with Spark installed:

	aws emr create-cluster --release-label emr-4.0.0 --applications Name=Spark --ec2-attributes KeyName=myKey --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge --auto-terminate
 

- Create an Amazon EMR cluster with MapR M7 edition::

    aws emr create-cluster --applications Name=MapR,Args=--edition,m7,--version,4.0.2 --ami-version 3.3.2 --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge --auto-terminate

**12. Restore HBase data from backup when creating an Amazon EMR cluster**

Only supported with AMI versions. 

-Command::

    aws emr create-cluster --applications Name=HBase --restore-from-hbase-backup Dir=s3://myBucket/myBackup,BackupVersion=myBackupVersion --ami-version 3.1.0  --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge --auto-terminate

**13. To add Custom JAR steps to a cluster when creating an Amazon EMR cluster**

- Command::

    aws emr create-cluster --steps Type=CUSTOM_JAR,Name=CustomJAR,ActionOnFailure=CONTINUE,Jar=s3://myBucket/mytest.jar,Args=arg1,arg2,arg3 Type=CUSTOM_JAR,Name=CustomJAR,ActionOnFailure=CONTINUE,Jar=s3://myBucket/mytest.jar,MainClass=mymainclass,Args=arg1,arg2,arg3  --release-label emr-4.0.0  --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge --auto-terminate

- Custom JAR steps required parameters::

    Jar

- Custom JAR steps optional parameters::

    Type, Name, ActionOnFailure, Args

**14. To add Streaming steps when creating an Amazon EMR cluster**

- Command::

    aws emr create-cluster --steps Type=STREAMING,Name='Streaming Program',ActionOnFailure=CONTINUE,Args=[-files,s3://elasticmapreduce/samples/wordcount/wordSplitter.py,-mapper,wordSplitter.py,-reducer,aggregate,-input,s3://elasticmapreduce/samples/wordcount/input,-output,s3://mybucket/wordcount/output] --release-label emr-4.0.0  --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge --auto-terminate

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

**15. To use multiple files in a Streaming step (JSON only)**

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

    aws emr create-cluster --steps file://./multiplefiles.json --release-label emr-4.0.0 --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge --auto-terminate

**16. To add Hive steps when creating an Amazon EMR cluster**

- Command::

    aws emr create-cluster --steps Type=HIVE,Name='Hive program',ActionOnFailure=CONTINUE,ActionOnFailure=TERMINATE_CLUSTER,Args=[-f,s3://elasticmapreduce/samples/hive-ads/libs/model-build.q,-d,INPUT=s3://elasticmapreduce/samples/hive-ads/tables,-d,OUTPUT=s3://mybucket/hive-ads/output/2014-04-18/11-07-32,-d,LIBS=s3://elasticmapreduce/samples/hive-ads/libs] --applications Name=Hive --release-label emr-4.0.0  --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge
      
- Hive steps required parameters::

    Type, Args

- Hive steps optional parameters::

    Name, ActionOnFailure

**17. To add Pig steps when creating an Amazon EMR cluster**

- Command::

    aws emr create-cluster --steps Type=PIG,Name='Pig program',ActionOnFailure=CONTINUE,Args=[-f,s3://elasticmapreduce/samples/pig-apache/do-reports2.pig,-p,INPUT=s3://elasticmapreduce/samples/pig-apache/input,-p,OUTPUT=s3://mybucket/pig-apache/output] --applications Name=Pig --release-label emr-4.0.0  --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge

- Pig steps required parameters::

    Type, Args

- Pig steps optional parameters::

    Name, ActionOnFailure

**18. To add Impala steps when creating an Amazon EMR cluster**

- Command::

    aws emr create-cluster --steps Type=CUSTOM_JAR,Name='Wikipedia Impala program',ActionOnFailure=CONTINUE,Jar=s3://elasticmapreduce/libs/script-runner/script-runner.jar,Args="/home/hadoop/impala/examples/wikipedia/wikipedia-with-s3distcp.sh" Type=IMPALA,Name='Impala program',ActionOnFailure=CONTINUE,Args=-f,--impala-script,s3://myimpala/input,--console-output-path,s3://myimpala/output --applications Name=Impala --ami-version 3.1.0  --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=m3.xlarge InstanceGroupType=CORE,InstanceCount=2,InstanceType=m3.xlarge 

- Impala steps required parameters::

    Type, Args

- Impala steps optional parameters::

    Name, ActionOnFailure
 

**19. To enable consistent view in EMRFS and change the RetryCount and Retry Period settings when creating an Amazon EMR cluster**

- Command::

    aws emr create-cluster --instance-type m3.xlarge --release-label emr-4.0.0 --emrfs Consistent=true,RetryCount=5,RetryPeriod=30
 
- Required parameters::
    
    Consistent=true

- JSON equivalent (contents of emrfs.json)::
 
    {
      "Consistent": true,
      "RetryCount": 5,
      "RetryPeriod": 30
    }
 
- Command (Using emrfs.json)::
 
    aws emr create-cluster --instance-type m3.xlarge --release-label emr-4.0.0 --emrfs file://emrfs.json
 

**20. To enable consistent view with arguments e.g. change the DynamoDB read and write capacity when creating an Amazon EMR cluster**

- Command::

    aws emr create-cluster --instance-type m3.xlarge --release-label emr-4.0.0 --emrfs Consistent=true,RetryCount=5,RetryPeriod=30,Args=[fs.s3.consistent.metadata.read.capacity=600,fs.s3.consistent.metadata.write.capacity=300]

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
 
    aws emr create-cluster --instance-type m3.xlarge --release-label emr-4.0.0 --emrfs file://emrfs.json

**21. To enable Amazon S3 server-side encryption in EMRFS when creating an Amazon EMR cluster**
 
- Command (Use Encryption=ServerSide)::

    aws emr create-cluster --instance-type m3.xlarge --release-label emr-4.0.0 --emrfs Encryption=ServerSide
 
- Required parameters::
 
    Encryption=ServerSide
 
- Optional parameters::
 
    Args
 
- JSON equivalent (contents of emrfs.json)::
 
    {
      "Encryption": "ServerSide",
      "Args": ["fs.s3.serverSideEncryptionAlgorithm=AES256"]
    }
 
**22. To enable Amazon S3 client-side encryption using a key managed by AWS Key Management Service (KMS) in EMRFS when creating an Amazon EMR cluster**
 
- Command::
 
    aws emr create-cluster --instance-type m3.xlarge --release-label emr-4.0.0 --emrfs Encryption=ClientSide,ProviderType=KMS,KMSKeyId=myKMSKeyId
 
- Required parameters::
 
    Encryption=ClientSide, ProviderType=KMS, KMSKeyId
 
- Optional parameters::
 
    Args
 
- JSON equivalent (contents of emrfs.json)::
 
    {
      "Encryption": "ClientSide",
      "ProviderType": "KMS",
      "KMSKeyId": "myKMSKeyId"
    }
 
**23. To enable Amazon S3 client-side encryption with a custom encryption provider in EMRFS when creating an Amazon EMR cluster**
 
- Command::
 
    aws emr create-cluster --instance-type m3.xlarge --release-label emr-4.0.0 --emrfs Encryption=ClientSide,ProviderType=Custom,CustomProviderLocation=s3://mybucket/myfolder/provider.jar,CustomProviderClass=classname
 
- Required parameters::
 
    Encryption=ClientSide, ProviderType=Custom, CustomProviderLocation, CustomProviderClass
 
- Optional parameters::
 
    Args
 
- JSON equivalent (contents of emrfs.json)::
 
    {
      "Encryption": "ClientSide",
      "ProviderType": "Custom",
      "CustomProviderLocation": "s3://mybucket/myfolder/provider.jar",
      "CustomProviderClass": "classname"
    }

**24. To enable Amazon S3 client-side encryption with a custom encryption provider in EMRFS and passing arguments expected by the class**
 
- Command::

    aws emr create-cluster --release-label emr-4.0.0 --instance-type m3.xlarge --instance-count 2 --emrfs Encryption=ClientSide,ProviderName=myProvider,CustomProviderLocation=s3://mybucket/myfolder/myprovider.jar,CustomProviderClass=classname,Args=[myProvider.arg1=value1,myProvider.arg2=value2]
 
- Required parameters::
 
    Encryption=ClientSide, ProviderType=Custom, CustomProviderLocation, CustomProviderClass
 
- Optional parameters::
 
    Args (expected by CustomProviderClass, passed to emrfs-site.xml using configure-hadoop bootstrap action)
 
- JSON equivalent (contents of emrfs.json)::
 
    {
      "Encryption": "ClientSide",
      "ProviderType": "Custom",
      "CustomProviderLocation": "s3://mybucket/myfolder/provider.jar",
      "CustomProviderClass": "classname"
    }
    
 **25. Create a cluster with EBS volumes configured to the instance groups:
    to create an Amazon EMR cluster**

- Create a cluster with multiple EBS volumes attached to the CORE instance group. EBS volumes can be attached to MASTER, CORE, and TASK instance groups. For instance groups with EBS configurations, which have an embedded JSON structure, you should enclose the entire instance group argument with single quotes. For instance groups with no EBS configuration, using single quotes is optional.
- Command::

    aws emr create-cluster --release-label emr-4.2.0  --use-default-roles --instance-groups InstanceGroupType=MASTER,InstanceCount=1,InstanceType=d2.xlarge 'InstanceGroupType=CORE,InstanceCount=2,InstanceType=d2.xlarge,EbsConfiguration={EbsOptimized=true,EbsBlockDeviceConfigs=[{VolumeSpecification={VolumeType=gp2,SizeInGB=100}},{VolumeSpecification={VolumeType=io1,SizeInGB=100,Iops=100},VolumesPerInstance=4}]}' --auto-terminate

- Create a cluster with multiple EBS volumes attached to the MASTER instance group. 
- Command::

    aws emr create-cluster --release-label emr-4.2.0 --use-default-roles --instance-groups 'InstanceGroupType=MASTER, InstanceCount=1, InstanceType=d2.xlarge, EbsConfiguration={EbsOptimized=true, EbsBlockDeviceConfigs=[{VolumeSpecification={VolumeType=io1, SizeInGB=100, Iops=100}},{VolumeSpecification={VolumeType=standard,SizeInGB=50},VolumesPerInstance=3}]}' InstanceGroupType=CORE,InstanceCount=2,InstanceType=d2.xlarge --auto-terminate

- Required parameters::
    
    VolumeType, SizeInGB if EbsBlockDeviceConfigs specified