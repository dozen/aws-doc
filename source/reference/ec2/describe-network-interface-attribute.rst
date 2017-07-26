[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-network-interface-attribute:


************************************
describe-network-interface-attribute
************************************



===========
Description
===========



Describes a network interface attribute. You can specify only one attribute at a time.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeNetworkInterfaceAttribute>`_


========
Synopsis
========

::

    describe-network-interface-attribute
  [--attribute <value>]
  [--dry-run | --no-dry-run]
  --network-interface-id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--attribute`` (string)


  The attribute of the network interface. This parameter is required.

  

  Possible values:

  
  *   ``description``

  
  *   ``groupSet``

  
  *   ``sourceDestCheck``

  
  *   ``attachment``

  

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--network-interface-id`` (string)


  The ID of the network interface.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe the attachment attribute of a network interface**

This example command describes the ``attachment`` attribute of the specified network interface.

Command::

  aws ec2 describe-network-interface-attribute --network-interface-id eni-686ea200 --attribute attachment
  
Output::

  {
    "NetworkInterfaceId": "eni-686ea200",
    "Attachment": {
        "Status": "attached",
        "DeviceIndex": 0,
        "AttachTime": "2015-05-21T20:02:20.000Z",
        "InstanceId": "i-1234567890abcdef0",
        "DeleteOnTermination": true,
        "AttachmentId": "eni-attach-43348162",
        "InstanceOwnerId": "123456789012"
    }
  }

**To describe the description attribute of a network interface**

This example command describes the ``description`` attribute of the specified network interface.

Command::

  aws ec2 describe-network-interface-attribute --network-interface-id eni-686ea200 --attribute description 
  
Output::

  {
    "NetworkInterfaceId": "eni-686ea200",
    "Description": {
        "Value": "My description"
    }
  }

**To describe the groupSet attribute of a network interface**

This example command describes the ``groupSet`` attribute of the specified network interface.

Command::

  aws ec2 describe-network-interface-attribute --network-interface-id eni-686ea200 --attribute groupSet
  
Output::

  {
    "NetworkInterfaceId": "eni-686ea200",
    "Groups": [
        {
            "GroupName": "my-security-group",
            "GroupId": "sg-903004f8"
        }
    ]
  }

**To describe the sourceDestCheck attribute of a network interface**

This example command describes the ``sourceDestCheck`` attribute of the specified network interface.

Command::

  aws ec2 describe-network-interface-attribute --network-interface-id eni-686ea200 --attribute sourceDestCheck
  
Output::

  {
    "NetworkInterfaceId": "eni-686ea200",
    "SourceDestCheck": {
        "Value": true
    }
  }


======
Output
======

Attachment -> (structure)

  

  The attachment (if any) of the network interface.

  

  AttachTime -> (timestamp)

    

    The timestamp indicating when the attachment initiated.

    

    

  AttachmentId -> (string)

    

    The ID of the network interface attachment.

    

    

  DeleteOnTermination -> (boolean)

    

    Indicates whether the network interface is deleted when the instance is terminated.

    

    

  DeviceIndex -> (integer)

    

    The device index of the network interface attachment on the instance.

    

    

  InstanceId -> (string)

    

    The ID of the instance.

    

    

  InstanceOwnerId -> (string)

    

    The AWS account ID of the owner of the instance.

    

    

  Status -> (string)

    

    The attachment state.

    

    

  

Description -> (structure)

  

  The description of the network interface.

  

  Value -> (string)

    

    The attribute value. Note that the value is case-sensitive.

    

    

  

Groups -> (list)

  

  The security groups associated with the network interface.

  

  (structure)

    

    Describes a security group.

    

    GroupName -> (string)

      

      The name of the security group.

      

      

    GroupId -> (string)

      

      The ID of the security group.

      

      

    

  

NetworkInterfaceId -> (string)

  

  The ID of the network interface.

  

  

SourceDestCheck -> (structure)

  

  Indicates whether source/destination checking is enabled.

  

  Value -> (boolean)

    

    The attribute value. The valid values are ``true`` or ``false`` .

    

    

  

