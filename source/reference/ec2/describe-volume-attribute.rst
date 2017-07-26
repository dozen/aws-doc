[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-volume-attribute:


*************************
describe-volume-attribute
*************************



===========
Description
===========



Describes the specified attribute of the specified volume. You can specify only one attribute at a time.

 

For more information about EBS volumes, see `Amazon EBS Volumes`_ in the *Amazon Elastic Compute Cloud User Guide* .



========
Synopsis
========

::

    describe-volume-attribute
  [--dry-run | --no-dry-run]
  --volume-id <value>
  [--attribute <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--volume-id`` (string)


  The ID of the volume.

  

``--attribute`` (string)


  The instance attribute.

  

  Possible values:

  
  *   ``autoEnableIO``

  
  *   ``productCodes``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe a volume attribute**

This example command describes the ``autoEnableIo`` attribute of the volume with the ID ``vol-2725bc51``.

Command::

  aws ec2 describe-volume-attribute --volume-id vol-2725bc51 --attribute autoEnableIO

Output::

   {
       "AutoEnableIO": {
           "Value": false
       },
       "ProductCodes": [],
       "VolumeId": "vol-2725bc51"
   }

======
Output
======

VolumeId -> (string)

  

  The ID of the volume.

  

  

AutoEnableIO -> (structure)

  

  The state of ``autoEnableIO`` attribute.

  

  Value -> (boolean)

    

    Valid values are ``true`` or ``false`` .

    

    

  

ProductCodes -> (list)

  

  A list of product codes.

  

  (structure)

    

    Describes a product code.

    

    ProductCodeId -> (string)

      

      The product code.

      

      

    ProductCodeType -> (string)

      

      The type of product code.

      

      

    

  



.. _Amazon EBS Volumes: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSVolumes.html
