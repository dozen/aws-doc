[ :ref:`aws <cli:aws>` . :ref:`autoscaling <cli:aws autoscaling>` ]

.. _cli:aws autoscaling describe-launch-configurations:


******************************
describe-launch-configurations
******************************



===========
Description
===========



Describes one or more launch configurations.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/autoscaling-2011-01-01/DescribeLaunchConfigurations>`_


``describe-launch-configurations`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``LaunchConfigurations``


========
Synopsis
========

::

    describe-launch-configurations
  [--launch-configuration-names <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--launch-configuration-names`` (list)


  The launch configuration names. If you omit this parameter, all launch configurations are described.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe Auto Scaling launch configurations**

This example describes the specified launch configuration::

    aws autoscaling describe-launch-configurations --launch-configuration-names my-launch-config

The following is example output::

    {
        "LaunchConfigurations": [
            {
                "UserData": null,
                "EbsOptimized": false,
                "LaunchConfigurationARN": "arn:aws:autoscaling:us-west-2:123456789012:launchConfiguration:98d3b196-4cf9-4e88-8ca1-8547c24ced8b:launchConfigurationName/my-launch-config",
                "InstanceMonitoring": {
                    "Enabled": true
                },
                "ImageId": "ami-043a5034",
                "CreatedTime": "2014-05-07T17:39:28.599Z",
                "BlockDeviceMappings": [],
                "KeyName": null,
                "SecurityGroups": [
                    "sg-67ef0308"
                ],
                "LaunchConfigurationName": "my-launch-config",
                "KernelId": null,
                "RamdiskId": null,
                "InstanceType": "t1.micro",
                "AssociatePublicIpAddress": true
            }
        ]
    }

To return a specific number of launch configurations, use the ``max-items`` parameter::

    aws autoscaling describe-launch-configurations --max-items 1

The following is example output::

    {
        "NextToken": "Z3M3LMPEXAMPLE",
        "LaunchConfigurations": [
            {
                "UserData": null,
                "EbsOptimized": false,
                "LaunchConfigurationARN": "arn:aws:autoscaling:us-west-2:123456789012:launchConfiguration:98d3b196-4cf9-4e88-8ca1-8547c24ced8b:launchConfigurationName/my-launch-config",
                "InstanceMonitoring": {
                    "Enabled": true
                },
                "ImageId": "ami-043a5034",
                "CreatedTime": "2014-05-07T17:39:28.599Z",
                "BlockDeviceMappings": [],
                "KeyName": null,
                "SecurityGroups": [
                    "sg-67ef0308"
                ],
                "LaunchConfigurationName": "my-launch-config",
                "KernelId": null,
                "RamdiskId": null,
                "InstanceType": "t1.micro",
                "AssociatePublicIpAddress": true
            }
        ]
    }

If the output includes a ``NextToken`` field, there are more launch configurations. To get the additional launch configurations, use the value of this field with the ``starting-token`` parameter in a subsequent call as follows::

    aws autoscaling describe-launch-configurations --starting-token Z3M3LMPEXAMPLE


======
Output
======

LaunchConfigurations -> (list)

  

  The launch configurations.

  

  (structure)

    

    Describes a launch configuration.

    

    LaunchConfigurationName -> (string)

      

      The name of the launch configuration.

      

      

    LaunchConfigurationARN -> (string)

      

      The Amazon Resource Name (ARN) of the launch configuration.

      

      

    ImageId -> (string)

      

      The ID of the Amazon Machine Image (AMI).

      

      

    KeyName -> (string)

      

      The name of the key pair.

      

      

    SecurityGroups -> (list)

      

      The security groups to associate with the instances.

      

      (string)

        

        

      

    ClassicLinkVPCId -> (string)

      

      The ID of a ClassicLink-enabled VPC to link your EC2-Classic instances to. This parameter can only be used if you are launching EC2-Classic instances. For more information, see `ClassicLink <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/vpc-classiclink.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .

      

      

    ClassicLinkVPCSecurityGroups -> (list)

      

      The IDs of one or more security groups for the VPC specified in ``ClassicLinkVPCId`` . This parameter is required if you specify a ClassicLink-enabled VPC, and cannot be used otherwise. For more information, see `ClassicLink <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/vpc-classiclink.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .

      

      (string)

        

        

      

    UserData -> (string)

      

      The user data available to the instances.

      

      

    InstanceType -> (string)

      

      The instance type for the instances.

      

      

    KernelId -> (string)

      

      The ID of the kernel associated with the AMI.

      

      

    RamdiskId -> (string)

      

      The ID of the RAM disk associated with the AMI.

      

      

    BlockDeviceMappings -> (list)

      

      A block device mapping, which specifies the block devices for the instance.

      

      (structure)

        

        Describes a block device mapping.

        

        VirtualName -> (string)

          

          The name of the virtual device (for example, ``ephemeral0`` ).

          

          

        DeviceName -> (string)

          

          The device name exposed to the EC2 instance (for example, ``/dev/sdh`` or ``xvdh`` ).

          

          

        Ebs -> (structure)

          

          The information about the Amazon EBS volume.

          

          SnapshotId -> (string)

            

            The ID of the snapshot.

            

            

          VolumeSize -> (integer)

            

            The volume size, in GiB. For ``standard`` volumes, specify a value from 1 to 1,024. For ``io1`` volumes, specify a value from 4 to 16,384. For ``gp2`` volumes, specify a value from 1 to 16,384. If you specify a snapshot, the volume size must be equal to or larger than the snapshot size.

             

            Default: If you create a volume from a snapshot and you don't specify a volume size, the default is the snapshot size.

            

            

          VolumeType -> (string)

            

            The volume type. For more information, see `Amazon EBS Volume Types <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSVolumeTypes.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .

             

            Valid values: ``standard`` | ``io1`` | ``gp2``  

             

            Default: ``standard``  

            

            

          DeleteOnTermination -> (boolean)

            

            Indicates whether the volume is deleted on instance termination.

             

            Default: ``true``  

            

            

          Iops -> (integer)

            

            The number of I/O operations per second (IOPS) to provision for the volume.

             

            Constraint: Required when the volume type is ``io1`` .

            

            

          Encrypted -> (boolean)

            

            Indicates whether the volume should be encrypted. Encrypted EBS volumes must be attached to instances that support Amazon EBS encryption. Volumes that are created from encrypted snapshots are automatically encrypted. There is no way to create an encrypted volume from an unencrypted snapshot or an unencrypted volume from an encrypted snapshot. For more information, see `Amazon EBS Encryption <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSEncryption.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .

            

            

          

        NoDevice -> (boolean)

          

          Suppresses a device mapping.

           

          If this parameter is true for the root device, the instance might fail the EC2 health check. Auto Scaling launches a replacement instance if the instance fails the health check.

          

          

        

      

    InstanceMonitoring -> (structure)

      

      Controls whether instances in this group are launched with detailed (``true`` ) or basic (``false`` ) monitoring.

      

      Enabled -> (boolean)

        

        If ``True`` , instance monitoring is enabled.

        

        

      

    SpotPrice -> (string)

      

      The price to bid when launching Spot Instances.

      

      

    IamInstanceProfile -> (string)

      

      The name or Amazon Resource Name (ARN) of the instance profile associated with the IAM role for the instance.

      

      

    CreatedTime -> (timestamp)

      

      The creation date and time for the launch configuration.

      

      

    EbsOptimized -> (boolean)

      

      Controls whether the instance is optimized for EBS I/O (``true`` ) or not (``false`` ).

      

      

    AssociatePublicIpAddress -> (boolean)

      

      [EC2-VPC] Indicates whether to assign a public IP address to each instance.

      

      

    PlacementTenancy -> (string)

      

      The tenancy of the instance, either ``default`` or ``dedicated`` . An instance with ``dedicated`` tenancy runs in an isolated, single-tenant hardware and can only be launched into a VPC.

      

      

    

  

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  

