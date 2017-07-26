[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-volume-attribute:


*************************
describe-volume-attribute
*************************



===========
Description
===========



Describes the specified attribute of the specified volume. You can specify only one attribute at a time.

 

For more information about EBS volumes, see `Amazon EBS Volumes <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSVolumes.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeVolumeAttribute>`_


========
Synopsis
========

::

    describe-volume-attribute
  [--attribute <value>]
  --volume-id <value>
  [--dry-run | --no-dry-run]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--attribute`` (string)


  The attribute of the volume. This parameter is required.

  

  Possible values:

  
  *   ``autoEnableIO``

  
  *   ``productCodes``

  

  

``--volume-id`` (string)


  The ID of the volume.

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe a volume attribute**

This example command describes the ``autoEnableIo`` attribute of the volume with the ID ``vol-049df61146c4d7901``.

Command::

  aws ec2 describe-volume-attribute --volume-id vol-049df61146c4d7901 --attribute autoEnableIO

Output::

   {
       "AutoEnableIO": {
           "Value": false
       },
       "VolumeId": "vol-049df61146c4d7901"
   }


======
Output
======

AutoEnableIO -> (structure)

  

  The state of ``autoEnableIO`` attribute.

  

  Value -> (boolean)

    

    The attribute value. The valid values are ``true`` or ``false`` .

    

    

  

ProductCodes -> (list)

  

  A list of product codes.

  

  (structure)

    

    Describes a product code.

    

    ProductCodeId -> (string)

      

      The product code.

      

      

    ProductCodeType -> (string)

      

      The type of product code.

      

      

    

  

VolumeId -> (string)

  

  The ID of the volume.

  

  

