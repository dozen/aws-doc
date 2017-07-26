[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` . :ref:`wait <cli:aws ec2 wait>` ]

.. _cli:aws ec2 wait spot-instance-request-fulfilled:


*******************************
spot-instance-request-fulfilled
*******************************



===========
Description
===========

Wait until JMESPath query SpotInstanceRequests[].Status.Code returns fulfilled for all elements when polling with ``describe-spot-instance-requests``. It will poll every 15 seconds until a successful state has been reached. This will exit with a return code of 255 after 40 failed checks.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeSpotInstanceRequests>`_


========
Synopsis
========

::

    spot-instance-request-fulfilled
  [--filters <value>]
  [--dry-run | --no-dry-run]
  [--spot-instance-request-ids <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filters`` (list)


  One or more filters.

   

   
  * ``availability-zone-group`` - The Availability Zone group. 
   
  * ``create-time`` - The time stamp when the Spot instance request was created. 
   
  * ``fault-code`` - The fault code related to the request. 
   
  * ``fault-message`` - The fault message related to the request. 
   
  * ``instance-id`` - The ID of the instance that fulfilled the request. 
   
  * ``launch-group`` - The Spot instance launch group. 
   
  * ``launch.block-device-mapping.delete-on-termination`` - Indicates whether the Amazon EBS volume is deleted on instance termination. 
   
  * ``launch.block-device-mapping.device-name`` - The device name for the Amazon EBS volume (for example, ``/dev/sdh`` ). 
   
  * ``launch.block-device-mapping.snapshot-id`` - The ID of the snapshot used for the Amazon EBS volume. 
   
  * ``launch.block-device-mapping.volume-size`` - The size of the Amazon EBS volume, in GiB. 
   
  * ``launch.block-device-mapping.volume-type`` - The type of the Amazon EBS volume: ``gp2`` for General Purpose SSD, ``io1`` for Provisioned IOPS SSD, ``st1`` for Throughput Optimized HDD, ``sc1`` for Cold HDD, or ``standard`` for Magnetic. 
   
  * ``launch.group-id`` - The security group for the instance. 
   
  * ``launch.image-id`` - The ID of the AMI. 
   
  * ``launch.instance-type`` - The type of instance (for example, ``m3.medium`` ). 
   
  * ``launch.kernel-id`` - The kernel ID. 
   
  * ``launch.key-name`` - The name of the key pair the instance launched with. 
   
  * ``launch.monitoring-enabled`` - Whether monitoring is enabled for the Spot instance. 
   
  * ``launch.ramdisk-id`` - The RAM disk ID. 
   
  * ``network-interface.network-interface-id`` - The ID of the network interface. 
   
  * ``network-interface.device-index`` - The index of the device for the network interface attachment on the instance. 
   
  * ``network-interface.subnet-id`` - The ID of the subnet for the instance. 
   
  * ``network-interface.description`` - A description of the network interface. 
   
  * ``network-interface.private-ip-address`` - The primary private IP address of the network interface. 
   
  * ``network-interface.delete-on-termination`` - Indicates whether the network interface is deleted when the instance is terminated. 
   
  * ``network-interface.group-id`` - The ID of the security group associated with the network interface. 
   
  * ``network-interface.group-name`` - The name of the security group associated with the network interface. 
   
  * ``network-interface.addresses.primary`` - Indicates whether the IP address is the primary private IP address. 
   
  * ``product-description`` - The product description associated with the instance (``Linux/UNIX`` | ``Windows`` ). 
   
  * ``spot-instance-request-id`` - The Spot instance request ID. 
   
  * ``spot-price`` - The maximum hourly price for any Spot instance launched to fulfill the request. 
   
  * ``state`` - The state of the Spot instance request (``open`` | ``active`` | ``closed`` | ``cancelled`` | ``failed`` ). Spot bid status information can help you track your Amazon EC2 Spot instance requests. For more information, see `Spot Bid Status <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/spot-bid-status.html>`_ in the Amazon Elastic Compute Cloud User Guide. 
   
  * ``status-code`` - The short code describing the most recent evaluation of your Spot instance request. 
   
  * ``status-message`` - The message explaining the status of the Spot instance request. 
   
  * ``tag`` :*key* =*value* - The key/value combination of a tag assigned to the resource. Specify the key of the tag in the filter name and the value of the tag in the filter value. For example, for the tag Purpose=X, specify ``tag:Purpose`` for the filter name and ``X`` for the filter value. 
   
  * ``tag-key`` - The key of a tag assigned to the resource. This filter is independent of the ``tag-value`` filter. For example, if you use both the filter "tag-key=Purpose" and the filter "tag-value=X", you get any resources assigned both the tag key Purpose (regardless of what the tag's value is), and the tag value X (regardless of what the tag's key is). If you want to list only resources where Purpose is X, see the ``tag`` :*key* =*value* filter. 
   
  * ``tag-value`` - The value of a tag assigned to the resource. This filter is independent of the ``tag-key`` filter. 
   
  * ``type`` - The type of Spot instance request (``one-time`` | ``persistent`` ). 
   
  * ``launched-availability-zone`` - The Availability Zone in which the bid is launched. 
   
  * ``valid-from`` - The start date of the request. 
   
  * ``valid-until`` - The end date of the request. 
   

  



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



``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--spot-instance-request-ids`` (list)


  One or more Spot instance request IDs.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None