[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-instance-attribute:


***************************
describe-instance-attribute
***************************



===========
Description
===========



Describes the specified attribute of the specified instance. You can specify only one attribute at a time. Valid attribute values are: ``instanceType`` | ``kernel`` | ``ramdisk`` | ``userData`` | ``disableApiTermination`` | ``instanceInitiatedShutdownBehavior`` | ``rootDeviceName`` | ``blockDeviceMapping`` | ``productCodes`` | ``sourceDestCheck`` | ``groupSet`` | ``ebsOptimized`` | ``sriovNetSupport`` 



========
Synopsis
========

::

    describe-instance-attribute
  [--dry-run | --no-dry-run]
  --instance-id <value>
  --attribute <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--instance-id`` (string)


  The ID of the instance.

  

``--attribute`` (string)


  The instance attribute.

  

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

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe the instance type**

This example describes the instance type of the specified instance.

Command::

  aws ec2 describe-instance-attribute --instance-id i-5203422c --attribute instanceType

Output::

  {
      "InstanceId": "i-5203422c"
      "InstanceType": {
          "Value": "t1.micro"
      }
  }

**To describe the disableApiTermination attribute**

This example describes the ``disableApiTermination`` attribute of the specified instance.

Command::

  aws ec2 describe-instance-attribute --instance-id i-5203422c --attribute disableApiTermination

Output::

  {
      "InstanceId": "i-5203422c"
      "DisableApiTermination": {
          "Value": "false"
      }
  }

**To describe the block device mapping for an instance**

This example describes the ``blockDeviceMapping`` attribute of the specified instance.

Command::

  aws ec2 describe-instance-attribute --instance-id i-5203422c --attribute blockDeviceMapping

Output::

  {
      "InstanceId": "i-5203422c"
      "BlockDeviceMappings": [
          {
              "DeviceName": "/dev/sda1",
              "Ebs": {
                  "Status": "attached",
                  "DeleteOnTermination": true,
                  "VolumeId": "vol-615a1339",
                  "AttachTime": "2013-05-17T22:42:34.000Z"
              }
          },
          {
              "DeviceName": "/dev/sdf",
              "Ebs": {
                  "Status": "attached",
                  "DeleteOnTermination": false,
                  "VolumeId": "vol-9f54b8dc",
                  "AttachTime": "2013-09-10T23:07:00.000Z"
              }
          }
      ],
  }


======
Output
======

InstanceId -> (string)

  

  The ID of the instance.

  

  

InstanceType -> (structure)

  

  The instance type.

  

  Value -> (string)

    

    Valid values are case-sensitive and vary by action.

    

    

  

KernelId -> (structure)

  

  The kernel ID.

  

  Value -> (string)

    

    Valid values are case-sensitive and vary by action.

    

    

  

RamdiskId -> (structure)

  

  The RAM disk ID.

  

  Value -> (string)

    

    Valid values are case-sensitive and vary by action.

    

    

  

UserData -> (structure)

  

  The Base64-encoded MIME user data.

  

  Value -> (string)

    

    Valid values are case-sensitive and vary by action.

    

    

  

DisableApiTermination -> (structure)

  

  If the value is ``true`` , you can't terminate the instance through the Amazon EC2 console, CLI, or API; otherwise, you can.

  

  Value -> (boolean)

    

    Valid values are ``true`` or ``false`` .

    

    

  

InstanceInitiatedShutdownBehavior -> (structure)

  

  Indicates whether an instance stops or terminates when you initiate shutdown from the instance (using the operating system command for system shutdown).

  

  Value -> (string)

    

    Valid values are case-sensitive and vary by action.

    

    

  

RootDeviceName -> (structure)

  

  The name of the root device (for example, ``/dev/sda1`` or ``/dev/xvda`` ).

  

  Value -> (string)

    

    Valid values are case-sensitive and vary by action.

    

    

  

BlockDeviceMappings -> (list)

  

  The block device mapping of the instance.

  

  (structure)

    

    Describes a block device mapping.

    

    DeviceName -> (string)

      

      The device name exposed to the instance (for example, ``/dev/sdh`` or ``xvdh`` ).

      

      

    Ebs -> (structure)

      

      Parameters used to automatically set up EBS volumes when the instance is launched.

      

      VolumeId -> (string)

        

        The ID of the EBS volume.

        

        

      Status -> (string)

        

        The attachment state.

        

        

      AttachTime -> (timestamp)

        

        The time stamp when the attachment initiated.

        

        

      DeleteOnTermination -> (boolean)

        

        Indicates whether the volume is deleted on instance termination.

        

        

      

    

  

ProductCodes -> (list)

  

  A list of product codes.

  

  (structure)

    

    Describes a product code.

    

    ProductCodeId -> (string)

      

      The product code.

      

      

    ProductCodeType -> (string)

      

      The type of product code.

      

      

    

  

EbsOptimized -> (structure)

  

  Indicates whether the instance is optimized for EBS I/O.

  

  Value -> (boolean)

    

    Valid values are ``true`` or ``false`` .

    

    

  

SriovNetSupport -> (structure)

  

  The value to use for a resource attribute.

  

  Value -> (string)

    

    Valid values are case-sensitive and vary by action.

    

    

  

SourceDestCheck -> (structure)

  

  Indicates whether source/destination checking is enabled. A value of ``true`` means checking is enabled, and ``false`` means checking is disabled. This value must be ``false`` for a NAT instance to perform NAT.

  

  Value -> (boolean)

    

    Valid values are ``true`` or ``false`` .

    

    

  

Groups -> (list)

  

  The security groups associated with the instance.

  

  (structure)

    

    Describes a security group.

    

    GroupName -> (string)

      

      The name of the security group.

      

      

    GroupId -> (string)

      

      The ID of the security group.

      

      

    

  

