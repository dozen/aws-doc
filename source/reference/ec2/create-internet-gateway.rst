[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-internet-gateway:


***********************
create-internet-gateway
***********************



===========
Description
===========



Creates an Internet gateway for use with a VPC. After creating the Internet gateway, you attach it to a VPC using  attach-internet-gateway .

 

For more information about your VPC and Internet gateway, see the `Amazon Virtual Private Cloud User Guide`_ .



========
Synopsis
========

::

    create-internet-gateway
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To create an Internet gateway**

This example creates an Internet gateway.

Command::

  aws ec2 create-internet-gateway 

Output::

  {
      "InternetGateway": {
          "Tags": [],
          "InternetGatewayId": "igw-c0a643a9",
          "Attachments": []
      }
  }

======
Output
======

InternetGateway -> (structure)

  

  Information about the Internet gateway.

  

  InternetGatewayId -> (string)

    

    The ID of the Internet gateway.

    

    

  Attachments -> (list)

    

    Any VPCs attached to the Internet gateway.

    

    (structure)

      

      Describes the attachment of a VPC to an Internet gateway.

      

      VpcId -> (string)

        

        The ID of the VPC.

        

        

      State -> (string)

        

        The current state of the attachment.

        

        

      

    

  Tags -> (list)

    

    Any tags assigned to the Internet gateway.

    

    (structure)

      

      Describes a tag.

      

      Key -> (string)

        

        The key of the tag. 

         

        Constraints: Tag keys are case-sensitive and accept a maximum of 127 Unicode characters. May not begin with ``aws:`` 

        

        

      Value -> (string)

        

        The value of the tag.

         

        Constraints: Tag values are case-sensitive and accept a maximum of 255 Unicode characters.

        

        

      

    

  



.. _Amazon Virtual Private Cloud User Guide: http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/
