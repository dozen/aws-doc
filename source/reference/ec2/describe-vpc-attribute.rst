[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-vpc-attribute:


**********************
describe-vpc-attribute
**********************



===========
Description
===========



Describes the specified attribute of the specified VPC. You can specify only one attribute at a time.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeVpcAttribute>`_


========
Synopsis
========

::

    describe-vpc-attribute
  --attribute <value>
  --vpc-id <value>
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--attribute`` (string)


  The VPC attribute.

  

  Possible values:

  
  *   ``enableDnsSupport``

  
  *   ``enableDnsHostnames``

  

  

``--vpc-id`` (string)


  The ID of the VPC.

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe the enableDnsSupport attribute**

This example describes the ``enableDnsSupport`` attribute. This attribute indicates whether DNS resolution is enabled for the VPC. If this attribute is ``true``, the Amazon DNS server resolves DNS hostnames for your instances to their corresponding IP addresses; otherwise, it does not.

Command::

  aws ec2 describe-vpc-attribute --vpc-id vpc-a01106c2 --attribute enableDnsSupport

Output::

  {
      "VpcId": "vpc-a01106c2",
      "EnableDnsSupport": {
          "Value": true
      }
  }
  
**To describe the enableDnsHostnames attribute**

This example describes the ``enableDnsHostnames`` attribute. This attribute indicates whether the instances launched in the VPC get DNS hostnames. If this attribute is ``true``, instances in the VPC get DNS hostnames; otherwise, they do not.

Command::

  aws ec2 describe-vpc-attribute --vpc-id vpc-a01106c2 --attribute enableDnsHostnames

Output::

  {
      "VpcId": "vpc-a01106c2",
      "EnableDnsHostnames": {
          "Value": true
      }
  }

======
Output
======

VpcId -> (string)

  

  The ID of the VPC.

  

  

EnableDnsHostnames -> (structure)

  

  Indicates whether the instances launched in the VPC get DNS hostnames. If this attribute is ``true`` , instances in the VPC get DNS hostnames; otherwise, they do not.

  

  Value -> (boolean)

    

    The attribute value. The valid values are ``true`` or ``false`` .

    

    

  

EnableDnsSupport -> (structure)

  

  Indicates whether DNS resolution is enabled for the VPC. If this attribute is ``true`` , the Amazon DNS server resolves DNS hostnames for your instances to their corresponding IP addresses; otherwise, it does not.

  

  Value -> (boolean)

    

    The attribute value. The valid values are ``true`` or ``false`` .

    

    

  

