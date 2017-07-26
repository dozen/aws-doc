[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` . :ref:`wait <cli:aws ec2 wait>` ]

.. _cli:aws ec2 wait image-available:


***************
image-available
***************



===========
Description
===========

Wait until JMESPath query Images[].State returns available for all elements when polling with ``describe-images``. It will poll every 15 seconds until a successful state has been reached. This will exit with a return code of 255 after 40 failed checks.

========
Synopsis
========

::

    image-available
  [--dry-run | --no-dry-run]
  [--image-ids <value>]
  [--owners <value>]
  [--executable-users <value>]
  [--filters <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--image-ids`` (list)


  One or more image IDs.

   

  Default: Describes all images available to you.

  



Syntax::

  "string" "string" ...



``--owners`` (list)


  Filters the images by the owner. Specify an AWS account ID, ``amazon`` (owner is Amazon), ``aws-marketplace`` (owner is AWS Marketplace), ``self`` (owner is the sender of the request). Omitting this option returns all images for which you have launch permissions, regardless of ownership.

  



Syntax::

  "string" "string" ...



``--executable-users`` (list)


  Scopes the images by users with explicit launch permissions. Specify an AWS account ID, ``self`` (the sender of the request), or ``all`` (public AMIs).

  



Syntax::

  "string" "string" ...



``--filters`` (list)


  One or more filters.

   

   
  * ``architecture`` - The image architecture (``i386`` | ``x86_64`` ). 
   
  * ``block-device-mapping.delete-on-termination`` - A no-dry-run value that indicates whether the Amazon EBS volume is deleted on instance termination. 
   
  * ``block-device-mapping.device-name`` - The device name for the EBS volume (for example, ``/dev/sdh`` ). 
   
  * ``block-device-mapping.snapshot-id`` - The ID of the snapshot used for the EBS volume. 
   
  * ``block-device-mapping.volume-size`` - The volume size of the EBS volume, in GiB. 
   
  * ``block-device-mapping.volume-type`` - The volume type of the EBS volume (``gp2`` | ``standard`` | ``io1`` ). 
   
  * ``description`` - The description of the image (provided during image creation). 
   
  * ``hypervisor`` - The hypervisor type (``ovm`` | ``xen`` ). 
   
  * ``image-id`` - The ID of the image. 
   
  * ``image-type`` - The image type (``machine`` | ``kernel`` | ``ramdisk`` ). 
   
  * ``is-public`` - A no-dry-run that indicates whether the image is public. 
   
  * ``kernel-id`` - The kernel ID. 
   
  * ``manifest-location`` - The location of the image manifest. 
   
  * ``name`` - The name of the AMI (provided during image creation). 
   
  * ``owner-alias`` - The AWS account alias (for example, ``amazon`` ). 
   
  * ``owner-id`` - The AWS account ID of the image owner. 
   
  * ``platform`` - The platform. To only list Windows-based AMIs, use ``windows`` . 
   
  * ``product-code`` - The product code. 
   
  * ``product-code.type`` - The type of the product code (``devpay`` | ``marketplace`` ). 
   
  * ``ramdisk-id`` - The RAM disk ID. 
   
  * ``root-device-name`` - The name of the root device volume (for example, ``/dev/sda1`` ). 
   
  * ``root-device-type`` - The type of the root device volume (``ebs`` | ``instance-store`` ). 
   
  * ``state`` - The state of the image (``available`` | ``pending`` | ``failed`` ). 
   
  * ``state-reason-code`` - The reason code for the state change. 
   
  * ``state-reason-message`` - The message for the state change. 
   
  * ``tag`` :*key* =*value* - The key/value combination of a tag assigned to the resource. 
   
  * ``tag-key`` - The key of a tag assigned to the resource. This filter is independent of the tag-value filter. For example, if you use both the filter "tag-key=Purpose" and the filter "tag-value=X", you get any resources assigned both the tag key Purpose (regardless of what the tag's value is), and the tag value X (regardless of what the tag's key is). If you want to list only resources where Purpose is X, see the ``tag`` :*key* =*value* filter. 
   
  * ``tag-value`` - The value of a tag assigned to the resource. This filter is independent of the ``tag-key`` filter. 
   
  * ``virtualization-type`` - The virtualization type (``paravirtual`` | ``hvm`` ). 
   

  



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



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

None