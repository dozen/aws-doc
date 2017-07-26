[ :ref:`aws <cli:aws>` . :ref:`opsworks <cli:aws opsworks>` ]

.. _cli:aws opsworks describe-instances:


******************
describe-instances
******************



===========
Description
===========



Requests a description of a set of instances.

 

.. note::

   

  You must specify at least one of the parameters.

   

 

**Required Permissions** : To use this action, an IAM user must have a Show, Deploy, or Manage permissions level for the stack, or an attached policy that explicitly grants permissions. For more information on user permissions, see `Managing User Permissions`_ .



========
Synopsis
========

::

    describe-instances
  [--stack-id <value>]
  [--layer-id <value>]
  [--instance-ids <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--stack-id`` (string)


  A stack ID. If you use this parameter, ``describe-instances`` returns descriptions of the instances associated with the specified stack.

  

``--layer-id`` (string)


  A layer ID. If you use this parameter, ``describe-instances`` returns descriptions of the instances associated with the specified layer.

  

``--instance-ids`` (list)


  An array of instance IDs to be described. If you use this parameter, ``describe-instances`` returns a description of the specified instances. Otherwise, it returns a description of every instance.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe instances**

The following ``describe-instances`` commmand describes the instances in a specified stack::

  aws opsworks --region us-east-1 describe-instances --stack-id 8c428b08-a1a1-46ce-a5f8-feddc43771b8

**Note**: AWS OpsWorks CLI commands should set the region to ``us-east-1`` regardless of the stack's location.

*Output*: The following output example is for a stack with two instances. The first is a registered
EC2 instance, and the second was created by AWS OpsWorks.

::

  {
    "Instances": [
      {
        "StackId": "71c7ca72-55ae-4b6a-8ee1-a8dcded3fa0f",
        "PrivateDns": "ip-10-31-39-66.us-west-2.compute.internal",
        "LayerIds": [
          "26cf1d32-6876-42fa-bbf1-9cadc0bff938"
        ],
        "EbsOptimized": false,
        "ReportedOs": {
          "Version": "14.04",
          "Name": "ubuntu",
          "Family": "debian"
        },
        "Status": "online",
        "InstanceId": "4d6d1710-ded9-42a1-b08e-b043ad7af1e2",
        "SshKeyName": "US-West-2",
        "InfrastructureClass": "ec2",
        "RootDeviceVolumeId": "vol-d08ec6c1",
        "SubnetId": "subnet-b8de0ddd",
        "InstanceType": "t1.micro",
        "CreatedAt": "2015-02-24T20:52:49+00:00",
        "AmiId": "ami-35501205",
        "Hostname": "ip-192-0-2-0",
        "Ec2InstanceId": "i-5cd23551",
        "PublicDns": "ec2-192-0-2-0.us-west-2.compute.amazonaws.com",
        "SecurityGroupIds": [
          "sg-c4d3f0a1"
        ],
        "Architecture": "x86_64",
        "RootDeviceType": "ebs",
        "InstallUpdatesOnBoot": true,
        "Os": "Custom",
        "VirtualizationType": "paravirtual",
        "AvailabilityZone": "us-west-2a",
        "PrivateIp": "10.31.39.66",
        "PublicIp": "192.0.2.06",
        "RegisteredBy": "arn:aws:iam::123456789102:user/AWS/OpsWorks/OpsWorks-EC2Register-i-5cd23551"
      },
      {
        "StackId": "71c7ca72-55ae-4b6a-8ee1-a8dcded3fa0f",
        "PrivateDns": "ip-10-31-39-158.us-west-2.compute.internal",
        "SshHostRsaKeyFingerprint": "69:6b:7b:8b:72:f3:ed:23:01:00:05:bc:9f:a4:60:c1",
        "LayerIds": [
          "26cf1d32-6876-42fa-bbf1-9cadc0bff938"
        ],
        "EbsOptimized": false,
        "ReportedOs": {},
        "Status": "booting",
        "InstanceId": "9b137a0d-2f5d-4cc0-9704-13da4b31fdcb",
        "SshKeyName": "US-West-2",
        "InfrastructureClass": "ec2",
        "RootDeviceVolumeId": "vol-e09dd5f1",
        "SubnetId": "subnet-b8de0ddd",
        "InstanceProfileArn": "arn:aws:iam::123456789102:instance-profile/aws-opsworks-ec2-role",
        "InstanceType": "c3.large",
        "CreatedAt": "2015-02-24T21:29:33+00:00",
        "AmiId": "ami-9fc29baf",
        "SshHostDsaKeyFingerprint": "fc:87:95:c3:f5:e1:3b:9f:d2:06:6e:62:9a:35:27:e8",
        "Ec2InstanceId": "i-8d2dca80",
        "PublicDns": "ec2-192-0-2-1.us-west-2.compute.amazonaws.com",
        "SecurityGroupIds": [
          "sg-b022add5",
          "sg-b122add4"
        ],
        "Architecture": "x86_64",
        "RootDeviceType": "ebs",
        "InstallUpdatesOnBoot": true,
        "Os": "Amazon Linux 2014.09",
        "VirtualizationType": "paravirtual",
        "AvailabilityZone": "us-west-2a",
        "Hostname": "custom11",
        "PrivateIp": "10.31.39.158",
        "PublicIp": "192.0.2.0"
      }
    ]
  }

**More Information**

For more information, see Instances_ in the *AWS OpsWorks User Guide*.

.. _Instances: http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances.html



======
Output
======

Instances -> (list)

  

  An array of ``Instance`` objects that describe the instances.

  

  (structure)

    

    Describes an instance.

    

    AgentVersion -> (string)

      

      The agent version. This parameter is set to ``INHERIT`` if the instance inherits the default stack setting or to a a version number for a fixed agent version.

      

      

    AmiId -> (string)

      

      A custom AMI ID to be used to create the instance. For more information, see `Instances`_ 

      

      

    Architecture -> (string)

      

      The instance architecture: "i386" or "x86_64".

      

      

    AutoScalingType -> (string)

      

      For load-based or time-based instances, the type.

      

      

    AvailabilityZone -> (string)

      

      The instance Availability Zone. For more information, see `Regions and Endpoints`_ .

      

      

    BlockDeviceMappings -> (list)

      

      An array of ``BlockDeviceMapping`` objects that specify the instance's block device mappings.

      

      (structure)

        

        Describes a block device mapping. This data type maps directly to the Amazon EC2 `BlockDeviceMapping`_ data type. 

        

        DeviceName -> (string)

          

          The device name that is exposed to the instance, such as ``/dev/sdh`` . For the root device, you can use the explicit device name or you can set this parameter to ``ROOT_DEVICE`` and AWS OpsWorks will provide the correct device name.

          

          

        NoDevice -> (string)

          

          Suppresses the specified device included in the AMI's block device mapping.

          

          

        VirtualName -> (string)

          

          The virtual device name. For more information, see `BlockDeviceMapping`_ .

          

          

        Ebs -> (structure)

          

          An ``EBSBlockDevice`` that defines how to configure an Amazon EBS volume when the instance is launched.

          

          SnapshotId -> (string)

            

            The snapshot ID.

            

            

          Iops -> (integer)

            

            The number of I/O operations per second (IOPS) that the volume supports. For more information, see `EbsBlockDevice`_ .

            

            

          VolumeSize -> (integer)

            

            The volume size, in GiB. For more information, see `EbsBlockDevice`_ .

            

            

          VolumeType -> (string)

            

            The volume type. ``gp2`` for General Purpose (SSD) volumes, ``io1`` for Provisioned IOPS (SSD) volumes, and ``standard`` for Magnetic volumes.

            

            

          DeleteOnTermination -> (boolean)

            

            Whether the volume is deleted on instance termination.

            

            

          

        

      

    CreatedAt -> (string)

      

      The time that the instance was created.

      

      

    EbsOptimized -> (boolean)

      

      Whether this is an Amazon EBS-optimized instance.

      

      

    Ec2InstanceId -> (string)

      

      The ID of the associated Amazon EC2 instance.

      

      

    EcsClusterArn -> (string)

      

      For container instances, the Amazon ECS cluster's ARN.

      

      

    EcsContainerInstanceArn -> (string)

      

      For container instances, the instance's ARN.

      

      

    ElasticIp -> (string)

      

      The instance `Elastic IP address`_ .

      

      

    Hostname -> (string)

      

      The instance host name.

      

      

    InfrastructureClass -> (string)

      

      For registered instances, the infrastructure class: ``ec2`` or ``on-premises`` .

      

      

    InstallUpdatesOnBoot -> (boolean)

      

      Whether to install operating system and package updates when the instance boots. The default value is ``true`` . If this value is set to ``false`` , you must then update your instances manually by using  create-deployment to run the ``update_dependencies`` stack command or by manually running ``yum`` (Amazon Linux) or ``apt-get`` (Ubuntu) on the instances. 

       

      .. note::

         

        We strongly recommend using the default value of ``true`` , to ensure that your instances have the latest security updates.

         

      

      

    InstanceId -> (string)

      

      The instance ID.

      

      

    InstanceProfileArn -> (string)

      

      The ARN of the instance's IAM profile. For more information about IAM ARNs, see `Using Identifiers`_ .

      

      

    InstanceType -> (string)

      

      The instance type, such as ``t2.micro`` .

      

      

    LastServiceErrorId -> (string)

      

      The ID of the last service error. For more information, call  describe-service-errors .

      

      

    LayerIds -> (list)

      

      An array containing the instance layer IDs.

      

      (string)

        

        

      

    Os -> (string)

      

      The instance's operating system.

      

      

    Platform -> (string)

      

      The instance's platform.

      

      

    PrivateDns -> (string)

      

      The The instance's private DNS name.

      

      

    PrivateIp -> (string)

      

      The instance's private IP address.

      

      

    PublicDns -> (string)

      

      The instance public DNS name.

      

      

    PublicIp -> (string)

      

      The instance public IP address.

      

      

    RegisteredBy -> (string)

      

      For registered instances, who performed the registration.

      

      

    ReportedAgentVersion -> (string)

      

      The instance's reported AWS OpsWorks agent version.

      

      

    ReportedOs -> (structure)

      

      For registered instances, the reported operating system.

      

      Family -> (string)

        

        The operating system family.

        

        

      Name -> (string)

        

        The operating system name.

        

        

      Version -> (string)

        

        The operating system version.

        

        

      

    RootDeviceType -> (string)

      

      The instance's root device type. For more information, see `Storage for the Root Device`_ .

      

      

    RootDeviceVolumeId -> (string)

      

      The root device volume ID.

      

      

    SecurityGroupIds -> (list)

      

      An array containing the instance security group IDs.

      

      (string)

        

        

      

    SshHostDsaKeyFingerprint -> (string)

      

      The SSH key's Deep Security Agent (DSA) fingerprint.

      

      

    SshHostRsaKeyFingerprint -> (string)

      

      The SSH key's RSA fingerprint.

      

      

    SshKeyName -> (string)

      

      The instance's Amazon EC2 key-pair name.

      

      

    StackId -> (string)

      

      The stack ID.

      

      

    Status -> (string)

      

      The instance status:

       

       
      * ``booting``  
       
      * ``connection_lost``  
       
      * ``online``  
       
      * ``pending``  
       
      * ``rebooting``  
       
      * ``requested``  
       
      * ``running_setup``  
       
      * ``setup_failed``  
       
      * ``shutting_down``  
       
      * ``start_failed``  
       
      * ``stopped``  
       
      * ``stopping``  
       
      * ``terminated``  
       
      * ``terminating``  
       

      

      

    SubnetId -> (string)

      

      The instance's subnet ID; applicable only if the stack is running in a VPC.

      

      

    VirtualizationType -> (string)

      

      The instance's virtualization type: ``paravirtual`` or ``hvm`` .

      

      

    

  



.. _Storage for the Root Device: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ComponentsAMIs.html#storage-for-the-root-device
.. _BlockDeviceMapping: http://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_BlockDeviceMapping.html
.. _Using Identifiers: http://docs.aws.amazon.com/IAM/latest/UserGuide/Using_Identifiers.html
.. _Regions and Endpoints: http://docs.aws.amazon.com/general/latest/gr/rande.html
.. _Instances: http://docs.aws.amazon.com/opsworks/latest/userguide/workinginstances-custom-ami.html
.. _Elastic IP address: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html
.. _Managing User Permissions: http://docs.aws.amazon.com/opsworks/latest/userguide/opsworks-security-users.html
.. _EbsBlockDevice: http://docs.aws.amazon.com/AWSEC2/latest/APIReference/API_EbsBlockDevice.html
