[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 modify-image-attribute:


**********************
modify-image-attribute
**********************



===========
Description
===========



Modifies the specified attribute of the specified AMI. You can specify only one attribute at a time.

 

.. note::

   

  AWS Marketplace product codes cannot be modified. Images with an AWS Marketplace product code cannot be made public.

   

 

.. note::

   

  The SriovNetSupport enhanced networking attribute cannot be changed using this command. Instead, enable SriovNetSupport on an instance and create an AMI from the instance. This will result in an image with SriovNetSupport enabled.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/ModifyImageAttribute>`_


========
Synopsis
========

::

    modify-image-attribute
  [--attribute <value>]
  [--description <value>]
  --image-id <value>
  [--launch-permission <value>]
  [--operation-type <value>]
  [--product-codes <value>]
  [--user-groups <value>]
  [--user-ids <value>]
  [--value <value>]
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--attribute`` (string)


  The name of the attribute to modify.

  

``--description`` (structure)


  A description for the AMI.

  

``--image-id`` (string)


  The ID of the AMI.

  

``--launch-permission`` (structure)


  A launch permission modification.

  



Shorthand Syntax::

    Add=[{Group=string,UserId=string},{Group=string,UserId=string}],Remove=[{Group=string,UserId=string},{Group=string,UserId=string}]




JSON Syntax::

  {
    "Add": [
      {
        "Group": "all",
        "UserId": "string"
      }
      ...
    ],
    "Remove": [
      {
        "Group": "all",
        "UserId": "string"
      }
      ...
    ]
  }



``--operation-type`` (string)


  The operation type.

  

  Possible values:

  
  *   ``add``

  
  *   ``remove``

  

  

``--product-codes`` (list)


  One or more product codes. After you add a product code to an AMI, it can't be removed. This is only valid when modifying the ``productCodes`` attribute.

  



Syntax::

  "string" "string" ...



``--user-groups`` (list)


  One or more user groups. This is only valid when modifying the ``launchPermission`` attribute.

  



Syntax::

  "string" "string" ...



``--user-ids`` (list)


  One or more AWS account IDs. This is only valid when modifying the ``launchPermission`` attribute.

  



Syntax::

  "string" "string" ...



``--value`` (string)


  The value of the attribute being modified. This is only valid when modifying the ``description`` attribute.

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To make an AMI public**

This example makes the specified AMI public. If the command succeeds, no output is returned.

Command::

  aws ec2 modify-image-attribute --image-id ami-5731123e --launch-permission "{\"Add\": [{\"Group\":\"all\"}]}"

**To make an AMI private**

This example makes the specified AMI private. If the command succeeds, no output is returned.

Command::

  aws ec2 modify-image-attribute --image-id ami-5731123e --launch-permission "{\"Remove\": [{\"Group\":\"all\"}]}"

**To grant launch permission to an AWS account**

This example grants launch permissions to the specified AWS account. If the command succeeds, no output is returned.

Command::

  aws ec2 modify-image-attribute --image-id ami-5731123e --launch-permission "{\"Add\": [{\"UserId\":\"123456789012\"}]}"

**To removes launch permission from an AWS account**

This example removes launch permissions from the specified AWS account. If the command succeeds, no output is returned.

Command::

  aws ec2 modify-image-attribute --image-id ami-5731123e --launch-permission "{\"Remove\": [{\"UserId\":\"123456789012\"}]}"


======
Output
======

None