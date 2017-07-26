[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-instances:


******************
describe-instances
******************



===========
Description
===========



Describes one or more of your instances.

 

If you specify one or more instance IDs, Amazon EC2 returns information for those instances. If you do not specify instance IDs, Amazon EC2 returns information for all relevant instances. If you specify an instance ID that is not valid, an error is returned. If you specify an instance that you do not own, it is not included in the returned results.

 

Recently terminated instances might appear in the returned results. This interval is usually less than one hour.

 

If you describe instances in the rare case where an Availability Zone is experiencing a service disruption and you specify instance IDs that are in the affected zone, or do not specify any instance IDs at all, the call fails. If you describe instances and specify only instance IDs that are in an unaffected zone, the call works normally.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeInstances>`_


``describe-instances`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Reservations``


========
Synopsis
========

::

    describe-instances
  [--filters <value>]
  [--instance-ids <value>]
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filters`` (list)


  One or more filters.

   

   
  * ``affinity`` - The affinity setting for an instance running on a Dedicated Host (``default`` | ``host`` ). 
   
  * ``architecture`` - The instance architecture (``i386`` | ``x86_64`` ). 
   
  * ``availability-zone`` - The Availability Zone of the instance. 
   
  * ``block-device-mapping.attach-time`` - The attach time for an EBS volume mapped to the instance, for example, ``2010-09-15T17:15:20.000Z`` . 
   
  * ``block-device-mapping.delete-on-termination`` - A dry-run that indicates whether the EBS volume is deleted on instance termination. 
   
  * ``block-device-mapping.device-name`` - The device name for the EBS volume (for example, ``/dev/sdh`` or ``xvdh`` ). 
   
  * ``block-device-mapping.status`` - The status for the EBS volume (``attaching`` | ``attached`` | ``detaching`` | ``detached`` ). 
   
  * ``block-device-mapping.volume-id`` - The volume ID of the EBS volume. 
   
  * ``client-token`` - The idempotency token you provided when you launched the instance. 
   
  * ``dns-name`` - The public DNS name of the instance. 
   
  * ``group-id`` - The ID of the security group for the instance. EC2-Classic only. 
   
  * ``group-name`` - The name of the security group for the instance. EC2-Classic only. 
   
  * ``host-id`` - The ID of the Dedicated Host on which the instance is running, if applicable. 
   
  * ``hypervisor`` - The hypervisor type of the instance (``ovm`` | ``xen`` ). 
   
  * ``iam-instance-profile.arn`` - The instance profile associated with the instance. Specified as an ARN. 
   
  * ``image-id`` - The ID of the image used to launch the instance. 
   
  * ``instance-id`` - The ID of the instance. 
   
  * ``instance-lifecycle`` - Indicates whether this is a Spot Instance or a Scheduled Instance (``spot`` | ``scheduled`` ). 
   
  * ``instance-state-code`` - The state of the instance, as a 16-bit unsigned integer. The high byte is an opaque internal value and should be ignored. The low byte is set based on the state represented. The valid values are: 0 (pending), 16 (running), 32 (shutting-down), 48 (terminated), 64 (stopping), and 80 (stopped). 
   
  * ``instance-state-name`` - The state of the instance (``pending`` | ``running`` | ``shutting-down`` | ``terminated`` | ``stopping`` | ``stopped`` ). 
   
  * ``instance-type`` - The type of instance (for example, ``t2.micro`` ). 
   
  * ``instance.group-id`` - The ID of the security group for the instance.  
   
  * ``instance.group-name`` - The name of the security group for the instance.  
   
  * ``ip-address`` - The public IPv4 address of the instance. 
   
  * ``kernel-id`` - The kernel ID. 
   
  * ``key-name`` - The name of the key pair used when the instance was launched. 
   
  * ``launch-index`` - When launching multiple instances, this is the index for the instance in the launch group (for example, 0, 1, 2, and so on).  
   
  * ``launch-time`` - The time when the instance was launched. 
   
  * ``monitoring-state`` - Indicates whether detailed monitoring is enabled (``disabled`` | ``enabled`` ). 
   
  * ``network-interface.addresses.private-ip-address`` - The private IPv4 address associated with the network interface. 
   
  * ``network-interface.addresses.primary`` - Specifies whether the IPv4 address of the network interface is the primary private IPv4 address. 
   
  * ``network-interface.addresses.association.public-ip`` - The ID of the association of an Elastic IP address (IPv4) with a network interface. 
   
  * ``network-interface.addresses.association.ip-owner-id`` - The owner ID of the private IPv4 address associated with the network interface. 
   
  * ``network-interface.association.public-ip`` - The address of the Elastic IP address (IPv4) bound to the network interface. 
   
  * ``network-interface.association.ip-owner-id`` - The owner of the Elastic IP address (IPv4) associated with the network interface. 
   
  * ``network-interface.association.allocation-id`` - The allocation ID returned when you allocated the Elastic IP address (IPv4) for your network interface. 
   
  * ``network-interface.association.association-id`` - The association ID returned when the network interface was associated with an IPv4 address. 
   
  * ``network-interface.attachment.attachment-id`` - The ID of the interface attachment. 
   
  * ``network-interface.attachment.instance-id`` - The ID of the instance to which the network interface is attached. 
   
  * ``network-interface.attachment.instance-owner-id`` - The owner ID of the instance to which the network interface is attached. 
   
  * ``network-interface.attachment.device-index`` - The device index to which the network interface is attached. 
   
  * ``network-interface.attachment.status`` - The status of the attachment (``attaching`` | ``attached`` | ``detaching`` | ``detached`` ). 
   
  * ``network-interface.attachment.attach-time`` - The time that the network interface was attached to an instance. 
   
  * ``network-interface.attachment.delete-on-termination`` - Specifies whether the attachment is deleted when an instance is terminated. 
   
  * ``network-interface.availability-zone`` - The Availability Zone for the network interface. 
   
  * ``network-interface.description`` - The description of the network interface. 
   
  * ``network-interface.group-id`` - The ID of a security group associated with the network interface. 
   
  * ``network-interface.group-name`` - The name of a security group associated with the network interface. 
   
  * ``network-interface.ipv6-addresses.ipv6-address`` - The IPv6 address associated with the network interface. 
   
  * ``network-interface.mac-address`` - The MAC address of the network interface. 
   
  * ``network-interface.network-interface-id`` - The ID of the network interface. 
   
  * ``network-interface.owner-id`` - The ID of the owner of the network interface. 
   
  * ``network-interface.private-dns-name`` - The private DNS name of the network interface. 
   
  * ``network-interface.requester-id`` - The requester ID for the network interface. 
   
  * ``network-interface.requester-managed`` - Indicates whether the network interface is being managed by AWS. 
   
  * ``network-interface.status`` - The status of the network interface (``available`` ) | ``in-use`` ). 
   
  * ``network-interface.source-dest-check`` - Whether the network interface performs source/destination checking. A value of ``true`` means checking is enabled, and ``false`` means checking is disabled. The value must be ``false`` for the network interface to perform network address translation (NAT) in your VPC. 
   
  * ``network-interface.subnet-id`` - The ID of the subnet for the network interface. 
   
  * ``network-interface.vpc-id`` - The ID of the VPC for the network interface. 
   
  * ``owner-id`` - The AWS account ID of the instance owner. 
   
  * ``placement-group-name`` - The name of the placement group for the instance. 
   
  * ``platform`` - The platform. Use ``windows`` if you have Windows instances; otherwise, leave blank. 
   
  * ``private-dns-name`` - The private IPv4 DNS name of the instance. 
   
  * ``private-ip-address`` - The private IPv4 address of the instance. 
   
  * ``product-code`` - The product code associated with the AMI used to launch the instance. 
   
  * ``product-code.type`` - The type of product code (``devpay`` | ``marketplace`` ). 
   
  * ``ramdisk-id`` - The RAM disk ID. 
   
  * ``reason`` - The reason for the current state of the instance (for example, shows "User Initiated [date]" when you stop or terminate the instance). Similar to the state-reason-code filter. 
   
  * ``requester-id`` - The ID of the entity that launched the instance on your behalf (for example, AWS Management Console, Auto Scaling, and so on). 
   
  * ``reservation-id`` - The ID of the instance's reservation. A reservation ID is created any time you launch an instance. A reservation ID has a one-to-one relationship with an instance launch request, but can be associated with more than one instance if you launch multiple instances using the same launch request. For example, if you launch one instance, you'll get one reservation ID. If you launch ten instances using the same launch request, you'll also get one reservation ID. 
   
  * ``root-device-name`` - The name of the root device for the instance (for example, ``/dev/sda1`` or ``/dev/xvda`` ). 
   
  * ``root-device-type`` - The type of root device that the instance uses (``ebs`` | ``instance-store`` ). 
   
  * ``source-dest-check`` - Indicates whether the instance performs source/destination checking. A value of ``true`` means that checking is enabled, and ``false`` means checking is disabled. The value must be ``false`` for the instance to perform network address translation (NAT) in your VPC.  
   
  * ``spot-instance-request-id`` - The ID of the Spot instance request. 
   
  * ``state-reason-code`` - The reason code for the state change. 
   
  * ``state-reason-message`` - A message that describes the state change. 
   
  * ``subnet-id`` - The ID of the subnet for the instance. 
   
  * ``tag`` :*key* =*value* - The key/value combination of a tag assigned to the resource. Specify the key of the tag in the filter name and the value of the tag in the filter value. For example, for the tag Purpose=X, specify ``tag:Purpose`` for the filter name and ``X`` for the filter value. 
   
  * ``tag-key`` - The key of a tag assigned to the resource. This filter is independent of the ``tag-value`` filter. For example, if you use both the filter "tag-key=Purpose" and the filter "tag-value=X", you get any resources assigned both the tag key Purpose (regardless of what the tag's value is), and the tag value X (regardless of what the tag's key is). If you want to list only resources where Purpose is X, see the ``tag`` :*key* =*value* filter. 
   
  * ``tag-value`` - The value of a tag assigned to the resource. This filter is independent of the ``tag-key`` filter. 
   
  * ``tenancy`` - The tenancy of an instance (``dedicated`` | ``default`` | ``host`` ). 
   
  * ``virtualization-type`` - The virtualization type of the instance (``paravirtual`` | ``hvm`` ). 
   
  * ``vpc-id`` - The ID of the VPC that the instance is running in. 
   

  



Shorthand Syntax::

    Name=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Values": ["string", ...]
    }
    ...
  ]



``--instance-ids`` (list)


  One or more instance IDs.

   

  Default: Describes all your instances.

  



Syntax::

  "string" "string" ...



``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

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

**To describe an Amazon EC2 instance**

Command::

  aws ec2 describe-instances --instance-ids i-1234567890abcdef0

**To describe all instances with the instance type m1.small**

Command::

  aws ec2 describe-instances --filters "Name=instance-type,Values=m1.small"

**To describe all instances with a Owner tag**

Command::

  aws ec2 describe-instances --filters "Name=tag-key,Values=Owner"

**To describe all instances with a Purpose=test tag**

Command::

  aws ec2 describe-instances --filters "Name=tag:Purpose,Values=test"

**To describe an EC2 instance and filter the result to return the AMI ID, and all tags associated with the instance.**

Command::

  aws ec2 describe-instances --instance-id i-1234567890abcdef0 --query 'Reservations[*].Instances[*].[ImageId,Tags[*]]'

**To describe all instances, and return all instance IDs and AMI IDs, but only show the tag value where the tag key is "Application".**

Command::

  aws ec2 describe-instances --query 'Reservations[*].Instances[*].[InstanceId,ImageId,Tags[?Key==`Application`].Value]'


**To describe all EC2 instances that have an instance type of m1.small or m1.medium that are also in the us-west-2c Availability Zone**

Command::

  aws ec2 describe-instances --filters "Name=instance-type,Values=m1.small,m1.medium" "Name=availability-zone,Values=us-west-2c"
  
The following JSON input performs the same filtering.

Command::

  aws ec2 describe-instances --filters file://filters.json

filters.json::

  [
    {
      "Name": "instance-type",
      "Values": ["m1.small", "m1.medium"]
    },
    {
      "Name": "availability-zone",
      "Values": ["us-west-2c"]
    }
  ]

For more information, see `Using Amazon EC2 Instances`_ in the *AWS Command Line Interface User Guide*.

.. _`Using Amazon EC2 Instances`: http://docs.aws.amazon.com/cli/latest/userguide/cli-ec2-launch.html



======
Output
======

Reservations -> (list)

  

  Zero or more reservations.

  

  (structure)

    

    Describes a reservation.

    

    Groups -> (list)

      

      [EC2-Classic only] One or more security groups.

      

      (structure)

        

        Describes a security group.

        

        GroupName -> (string)

          

          The name of the security group.

          

          

        GroupId -> (string)

          

          The ID of the security group.

          

          

        

      

    Instances -> (list)

      

      One or more instances.

      

      (structure)

        

        Describes an instance.

        

        AmiLaunchIndex -> (integer)

          

          The AMI launch index, which can be used to find this instance in the launch group.

          

          

        ImageId -> (string)

          

          The ID of the AMI used to launch the instance.

          

          

        InstanceId -> (string)

          

          The ID of the instance.

          

          

        InstanceType -> (string)

          

          The instance type.

          

          

        KernelId -> (string)

          

          The kernel associated with this instance, if applicable.

          

          

        KeyName -> (string)

          

          The name of the key pair, if this instance was launched with an associated key pair.

          

          

        LaunchTime -> (timestamp)

          

          The time the instance was launched.

          

          

        Monitoring -> (structure)

          

          The monitoring for the instance.

          

          State -> (string)

            

            Indicates whether detailed monitoring is enabled. Otherwise, basic monitoring is enabled.

            

            

          

        Placement -> (structure)

          

          The location where the instance launched, if applicable.

          

          AvailabilityZone -> (string)

            

            The Availability Zone of the instance.

            

            

          Affinity -> (string)

            

            The affinity setting for the instance on the Dedicated Host. This parameter is not supported for the  import-instance command.

            

            

          GroupName -> (string)

            

            The name of the placement group the instance is in (for cluster compute instances).

            

            

          HostId -> (string)

            

            The ID of the Dedicated Host on which the instance resides. This parameter is not supported for the  import-instance command.

            

            

          Tenancy -> (string)

            

            The tenancy of the instance (if the instance is running in a VPC). An instance with a tenancy of ``dedicated`` runs on single-tenant hardware. The ``host`` tenancy is not supported for the  import-instance command.

            

            

          SpreadDomain -> (string)

            

            Reserved for future use.

            

            

          

        Platform -> (string)

          

          The value is ``Windows`` for Windows instances; otherwise blank.

          

          

        PrivateDnsName -> (string)

          

          (IPv4 only) The private DNS hostname name assigned to the instance. This DNS hostname can only be used inside the Amazon EC2 network. This name is not available until the instance enters the ``running`` state. 

           

          [EC2-VPC] The Amazon-provided DNS server will resolve Amazon-provided private DNS hostnames if you've enabled DNS resolution and DNS hostnames in your VPC. If you are not using the Amazon-provided DNS server in your VPC, your custom domain name servers must resolve the hostname as appropriate.

          

          

        PrivateIpAddress -> (string)

          

          The private IPv4 address assigned to the instance.

          

          

        ProductCodes -> (list)

          

          The product codes attached to this instance, if applicable.

          

          (structure)

            

            Describes a product code.

            

            ProductCodeId -> (string)

              

              The product code.

              

              

            ProductCodeType -> (string)

              

              The type of product code.

              

              

            

          

        PublicDnsName -> (string)

          

          (IPv4 only) The public DNS name assigned to the instance. This name is not available until the instance enters the ``running`` state. For EC2-VPC, this name is only available if you've enabled DNS hostnames for your VPC.

          

          

        PublicIpAddress -> (string)

          

          The public IPv4 address assigned to the instance, if applicable.

          

          

        RamdiskId -> (string)

          

          The RAM disk associated with this instance, if applicable.

          

          

        State -> (structure)

          

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

            

            

          

        StateTransitionReason -> (string)

          

          The reason for the most recent state transition. This might be an empty string.

          

          

        SubnetId -> (string)

          

          [EC2-VPC] The ID of the subnet in which the instance is running.

          

          

        VpcId -> (string)

          

          [EC2-VPC] The ID of the VPC in which the instance is running.

          

          

        Architecture -> (string)

          

          The architecture of the image.

          

          

        BlockDeviceMappings -> (list)

          

          Any block device mapping entries for the instance.

          

          (structure)

            

            Describes a block device mapping.

            

            DeviceName -> (string)

              

              The device name exposed to the instance (for example, ``/dev/sdh`` or ``xvdh`` ).

              

              

            Ebs -> (structure)

              

              Parameters used to automatically set up EBS volumes when the instance is launched.

              

              AttachTime -> (timestamp)

                

                The time stamp when the attachment initiated.

                

                

              DeleteOnTermination -> (boolean)

                

                Indicates whether the volume is deleted on instance termination.

                

                

              Status -> (string)

                

                The attachment state.

                

                

              VolumeId -> (string)

                

                The ID of the EBS volume.

                

                

              

            

          

        ClientToken -> (string)

          

          The idempotency token you provided when you launched the instance, if applicable.

          

          

        EbsOptimized -> (boolean)

          

          Indicates whether the instance is optimized for EBS I/O. This optimization provides dedicated throughput to Amazon EBS and an optimized configuration stack to provide optimal I/O performance. This optimization isn't available with all instance types. Additional usage charges apply when using an EBS Optimized instance.

          

          

        EnaSupport -> (boolean)

          

          Specifies whether enhanced networking with ENA is enabled.

          

          

        Hypervisor -> (string)

          

          The hypervisor type of the instance.

          

          

        IamInstanceProfile -> (structure)

          

          The IAM instance profile associated with the instance, if applicable.

          

          Arn -> (string)

            

            The Amazon Resource Name (ARN) of the instance profile.

            

            

          Id -> (string)

            

            The ID of the instance profile.

            

            

          

        InstanceLifecycle -> (string)

          

          Indicates whether this is a Spot instance or a Scheduled Instance.

          

          

        NetworkInterfaces -> (list)

          

          [EC2-VPC] One or more network interfaces for the instance.

          

          (structure)

            

            Describes a network interface.

            

            Association -> (structure)

              

              The association information for an Elastic IPv4 associated with the network interface.

              

              IpOwnerId -> (string)

                

                The ID of the owner of the Elastic IP address.

                

                

              PublicDnsName -> (string)

                

                The public DNS name.

                

                

              PublicIp -> (string)

                

                The public IP address or Elastic IP address bound to the network interface.

                

                

              

            Attachment -> (structure)

              

              The network interface attachment.

              

              AttachTime -> (timestamp)

                

                The time stamp when the attachment initiated.

                

                

              AttachmentId -> (string)

                

                The ID of the network interface attachment.

                

                

              DeleteOnTermination -> (boolean)

                

                Indicates whether the network interface is deleted when the instance is terminated.

                

                

              DeviceIndex -> (integer)

                

                The index of the device on the instance for the network interface attachment.

                

                

              Status -> (string)

                

                The attachment state.

                

                

              

            Description -> (string)

              

              The description.

              

              

            Groups -> (list)

              

              One or more security groups.

              

              (structure)

                

                Describes a security group.

                

                GroupName -> (string)

                  

                  The name of the security group.

                  

                  

                GroupId -> (string)

                  

                  The ID of the security group.

                  

                  

                

              

            Ipv6Addresses -> (list)

              

              One or more IPv6 addresses associated with the network interface.

              

              (structure)

                

                Describes an IPv6 address.

                

                Ipv6Address -> (string)

                  

                  The IPv6 address.

                  

                  

                

              

            MacAddress -> (string)

              

              The MAC address.

              

              

            NetworkInterfaceId -> (string)

              

              The ID of the network interface.

              

              

            OwnerId -> (string)

              

              The ID of the AWS account that created the network interface.

              

              

            PrivateDnsName -> (string)

              

              The private DNS name.

              

              

            PrivateIpAddress -> (string)

              

              The IPv4 address of the network interface within the subnet.

              

              

            PrivateIpAddresses -> (list)

              

              One or more private IPv4 addresses associated with the network interface.

              

              (structure)

                

                Describes a private IPv4 address.

                

                Association -> (structure)

                  

                  The association information for an Elastic IP address for the network interface.

                  

                  IpOwnerId -> (string)

                    

                    The ID of the owner of the Elastic IP address.

                    

                    

                  PublicDnsName -> (string)

                    

                    The public DNS name.

                    

                    

                  PublicIp -> (string)

                    

                    The public IP address or Elastic IP address bound to the network interface.

                    

                    

                  

                Primary -> (boolean)

                  

                  Indicates whether this IPv4 address is the primary private IP address of the network interface.

                  

                  

                PrivateDnsName -> (string)

                  

                  The private IPv4 DNS name.

                  

                  

                PrivateIpAddress -> (string)

                  

                  The private IPv4 address of the network interface.

                  

                  

                

              

            SourceDestCheck -> (boolean)

              

              Indicates whether to validate network traffic to or from this network interface.

              

              

            Status -> (string)

              

              The status of the network interface.

              

              

            SubnetId -> (string)

              

              The ID of the subnet.

              

              

            VpcId -> (string)

              

              The ID of the VPC.

              

              

            

          

        RootDeviceName -> (string)

          

          The root device name (for example, ``/dev/sda1`` or ``/dev/xvda`` ).

          

          

        RootDeviceType -> (string)

          

          The root device type used by the AMI. The AMI can use an EBS volume or an instance store volume.

          

          

        SecurityGroups -> (list)

          

          One or more security groups for the instance.

          

          (structure)

            

            Describes a security group.

            

            GroupName -> (string)

              

              The name of the security group.

              

              

            GroupId -> (string)

              

              The ID of the security group.

              

              

            

          

        SourceDestCheck -> (boolean)

          

          Specifies whether to enable an instance launched in a VPC to perform NAT. This controls whether source/destination checking is enabled on the instance. A value of ``true`` means checking is enabled, and ``false`` means checking is disabled. The value must be ``false`` for the instance to perform NAT. For more information, see `NAT Instances <http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_NAT_Instance.html>`_ in the *Amazon Virtual Private Cloud User Guide* .

          

          

        SpotInstanceRequestId -> (string)

          

          If the request is a Spot instance request, the ID of the request.

          

          

        SriovNetSupport -> (string)

          

          Specifies whether enhanced networking with the Intel 82599 Virtual Function interface is enabled.

          

          

        StateReason -> (structure)

          

          The reason for the most recent state transition.

          

          Code -> (string)

            

            The reason code for the state change.

            

            

          Message -> (string)

            

            The message for the state change.

             

             
            * ``Server.InsufficientInstanceCapacity`` : There was insufficient instance capacity to satisfy the launch request. 
             
            * ``Server.InternalError`` : An internal error occurred during instance launch, resulting in termination. 
             
            * ``Server.ScheduledStop`` : The instance was stopped due to a scheduled retirement. 
             
            * ``Server.SpotInstanceTermination`` : A Spot instance was terminated due to an increase in the market price. 
             
            * ``Client.InternalError`` : A client error caused the instance to terminate on launch. 
             
            * ``Client.InstanceInitiatedShutdown`` : The instance was shut down using the ``shutdown -h`` command from the instance. 
             
            * ``Client.UserInitiatedShutdown`` : The instance was shut down using the Amazon EC2 API. 
             
            * ``Client.VolumeLimitExceeded`` : The limit on the number of EBS volumes or total storage was exceeded. Decrease usage or request an increase in your limits. 
             
            * ``Client.InvalidSnapshot.NotFound`` : The specified snapshot was not found. 
             

            

            

          

        Tags -> (list)

          

          Any tags assigned to the instance.

          

          (structure)

            

            Describes a tag.

            

            Key -> (string)

              

              The key of the tag.

               

              Constraints: Tag keys are case-sensitive and accept a maximum of 127 Unicode characters. May not begin with ``aws:``  

              

              

            Value -> (string)

              

              The value of the tag.

               

              Constraints: Tag values are case-sensitive and accept a maximum of 255 Unicode characters.

              

              

            

          

        VirtualizationType -> (string)

          

          The virtualization type of the instance.

          

          

        

      

    OwnerId -> (string)

      

      The ID of the AWS account that owns the reservation.

      

      

    RequesterId -> (string)

      

      The ID of the requester that launched the instances on your behalf (for example, AWS Management Console or Auto Scaling).

      

      

    ReservationId -> (string)

      

      The ID of the reservation.

      

      

    

  

NextToken -> (string)

  

  The token to use to retrieve the next page of results. This value is ``null`` when there are no more results to return.

  

  

