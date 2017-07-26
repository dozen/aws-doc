[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-instance-attribute:


***************************
describe-instance-attribute
***************************



===========
Description
===========



Describes the specified attribute of the specified instance. You can specify only one attribute at a time. Valid attribute values are: ``instanceType`` | ``kernel`` | ``ramdisk`` | ``userData`` | ``disableApiTermination`` | ``instanceInitiatedShutdownBehavior`` | ``rootDeviceName`` | ``blockDeviceMapping`` | ``productCodes`` | ``sourceDestCheck`` | ``groupSet`` | ``ebsOptimized`` | ``sriovNetSupport``  



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeInstanceAttribute>`_


========
Synopsis
========

::

    describe-instance-attribute
  --attribute <value>
  [--dry-run | --no-dry-run]
  --instance-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--attribute`` (string)


  The instance attribute.

   

  Note: The ``enaSupport`` attribute is not supported at this time.

  

  Possible values:

  
  *   ``instanceType``

  
  *   ``kernel``

  
  *   ``ramdisk``

  
  *   ``userData``

  
  *   ``disableApiTermination``

  
  *   ``instanceInitiatedShutdownBehavior``

  
  *   ``rootDeviceName``

  
  *   ``blockDeviceMapping``

  
  *   ``productCodes``

  
  *   ``sourceDestCheck``

  
  *   ``groupSet``

  
  *   ``ebsOptimized``

  
  *   ``sriovNetSupport``

  
  *   ``enaSupport``

  

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--instance-id`` (string)


  The ID of the instance.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe the instance type**

This example describes the instance type of the specified instance.

Command::

  aws ec2 describe-instance-attribute --instance-id i-1234567890abcdef0 --attribute instanceType

Output::

  {
      "InstanceId": "i-1234567890abcdef0"
      "InstanceType": {
          "Value": "t1.micro"
      }
  }

**To describe the disableApiTermination attribute**

This example describes the ``disableApiTermination`` attribute of the specified instance.

Command::

  aws ec2 describe-instance-attribute --instance-id i-1234567890abcdef0 --attribute disableApiTermination

Output::

  {
  "InstanceId": "i-1234567890abcdef0"
      "DisableApiTermination": {
          "Value": "false"
      }
  }

**To describe the block device mapping for an instance**

This example describes the ``blockDeviceMapping`` attribute of the specified instance.

Command::

  aws ec2 describe-instance-attribute --instance-id i-1234567890abcdef0 --attribute blockDeviceMapping

Output::

  {
      "InstanceId": "i-1234567890abcdef0"
      "BlockDeviceMappings": [
          {
              "DeviceName": "/dev/sda1",
              "Ebs": {
                  "Status": "attached",
                  "DeleteOnTermination": true,
                  "VolumeId": "vol-049df61146c4d7901",
                  "AttachTime": "2013-05-17T22:42:34.000Z"
              }
          },
          {
              "DeviceName": "/dev/sdf",
              "Ebs": {
                  "Status": "attached",
                  "DeleteOnTermination": false,
                  "VolumeId": "vol-049df61146c4d7901",
                  "AttachTime": "2013-09-10T23:07:00.000Z"
              }
          }
      ],
  }


======
Output
======

Groups -> (list)

  

  The security groups associated with the instance.

  

  (structure)

    

    Describes a security group.

    

    GroupName -> (string)

      

      The name of the security group.

      

      

    GroupId -> (string)

      

      The ID of the security group.

      

      

    

  

BlockDeviceMappings -> (list)

  

  The block device mapping of the instance.

  

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

        

        

      

    

  

DisableApiTermination -> (structure)

  

  If the value is ``true`` , you can't terminate the instance through the Amazon EC2 console, CLI, or API; otherwise, you can.

  

  Value -> (boolean)

    

    The attribute value. The valid values are ``true`` or ``false`` .

    

    

  

EnaSupport -> (structure)

  

  Indicates whether enhanced networking with ENA is enabled.

  

  Value -> (boolean)

    

    The attribute value. The valid values are ``true`` or ``false`` .

    

    

  

EbsOptimized -> (structure)

  

  Indicates whether the instance is optimized for EBS I/O.

  

  Value -> (boolean)

    

    The attribute value. The valid values are ``true`` or ``false`` .

    

    

  

InstanceId -> (string)

  

  The ID of the instance.

  

  

InstanceInitiatedShutdownBehavior -> (structure)

  

  Indicates whether an instance stops or terminates when you initiate shutdown from the instance (using the operating system command for system shutdown).

  

  Value -> (string)

    

    The attribute value. Note that the value is case-sensitive.

    

    

  

InstanceType -> (structure)

  

  The instance type.

  

  Value -> (string)

    

    The attribute value. Note that the value is case-sensitive.

    

    

  

KernelId -> (structure)

  

  The kernel ID.

  

  Value -> (string)

    

    The attribute value. Note that the value is case-sensitive.

    

    

  

ProductCodes -> (list)

  

  A list of product codes.

  

  (structure)

    

    Describes a product code.

    

    ProductCodeId -> (string)

      

      The product code.

      

      

    ProductCodeType -> (string)

      

      The type of product code.

      

      

    

  

RamdiskId -> (structure)

  

  The RAM disk ID.

  

  Value -> (string)

    

    The attribute value. Note that the value is case-sensitive.

    

    

  

RootDeviceName -> (structure)

  

  The name of the root device (for example, ``/dev/sda1`` or ``/dev/xvda`` ).

  

  Value -> (string)

    

    The attribute value. Note that the value is case-sensitive.

    

    

  

SourceDestCheck -> (structure)

  

  Indicates whether source/destination checking is enabled. A value of ``true`` means checking is enabled, and ``false`` means checking is disabled. This value must be ``false`` for a NAT instance to perform NAT.

  

  Value -> (boolean)

    

    The attribute value. The valid values are ``true`` or ``false`` .

    

    

  

SriovNetSupport -> (structure)

  

  Indicates whether enhanced networking with the Intel 82599 Virtual Function interface is enabled.

  

  Value -> (string)

    

    The attribute value. Note that the value is case-sensitive.

    

    

  

UserData -> (structure)

  

  The user data.

  

  Value -> (string)

    

    The attribute value. Note that the value is case-sensitive.

    

    

  

