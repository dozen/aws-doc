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

  



========
Synopsis
========

::

    modify-image-attribute
  [--dry-run | --no-dry-run]
  --image-id <value>
  [--attribute <value>]
  [--operation-type <value>]
  [--user-ids <value>]
  [--user-groups <value>]
  [--product-codes <value>]
  [--value <value>]
  [--launch-permission <value>]
  [--description <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--image-id`` (string)


  The ID of the AMI.

  

``--attribute`` (string)


  The name of the attribute to modify.

  

``--operation-type`` (string)


  The operation type.

  

  Possible values:

  
  *   ``add``

  
  *   ``remove``

  

  

``--user-ids`` (list)


  One or more AWS account IDs. This is only valid when modifying the ``launchPermission`` attribute.

  



Syntax::

  "string" "string" ...



``--user-groups`` (list)


  One or more user groups. This is only valid when modifying the ``launchPermission`` attribute.

  



Syntax::

  "string" "string" ...



``--product-codes`` (list)


  One or more product codes. After you add a product code to an AMI, it can't be removed. This is only valid when modifying the ``productCodes`` attribute.

  



Syntax::

  "string" "string" ...



``--value`` (string)


  The value of the attribute being modified. This is only valid when modifying the ``description`` attribute.

  

``--launch-permission`` (structure)


  A launch permission modification.

  



Shorthand Syntax::

    Add=[{UserId=string,Group=string},{UserId=string,Group=string}],Remove=[{UserId=string,Group=string},{UserId=string,Group=string}]




JSON Syntax::

  {
    "Add": [
      {
        "UserId": "string",
        "Group": "all"
      }
      ...
    ],
    "Remove": [
      {
        "UserId": "string",
        "Group": "all"
      }
      ...
    ]
  }



``--description`` (structure)


  A description for the AMI.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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