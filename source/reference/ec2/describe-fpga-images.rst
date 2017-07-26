[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-fpga-images:


********************
describe-fpga-images
********************



===========
Description
===========



Describes one or more available Amazon FPGA Images (AFIs). These include public AFIs, private AFIs that you own, and AFIs owned by other AWS accounts for which you have load permissions.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeFpgaImages>`_


========
Synopsis
========

::

    describe-fpga-images
  [--dry-run | --no-dry-run]
  [--fpga-image-ids <value>]
  [--owners <value>]
  [--filters <value>]
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--fpga-image-ids`` (list)


  One or more AFI IDs.

  



Syntax::

  "string" "string" ...



``--owners`` (list)


  Filters the AFI by owner. Specify an AWS account ID, ``self`` (owner is the sender of the request), or an AWS owner alias (valid values are ``amazon`` | ``aws-marketplace`` ).

  



Syntax::

  "string" "string" ...



``--filters`` (list)


  One or more filters.

   

   
  * ``create-time`` - The creation time of the AFI. 
   
  * ``fpga-image-id`` - The FPGA image identifier (AFI ID). 
   
  * ``fpga-image-global-id`` - The global FPGA image identifier (AGFI ID). 
   
  * ``name`` - The name of the AFI. 
   
  * ``owner-id`` - The AWS account ID of the AFI owner. 
   
  * ``product-code`` - The product code. 
   
  * ``shell-version`` - The version of the AWS Shell that was used to create the bitstream. 
   
  * ``state`` - The state of the AFI (``pending`` | ``failed`` | ``available`` | ``unavailable`` ). 
   
  * ``tag`` :*key* =*value* - The key/value combination of a tag assigned to the resource. Specify the key of the tag in the filter name and the value of the tag in the filter value. For example, for the tag Purpose=X, specify ``tag:Purpose`` for the filter name and ``X`` for the filter value. 
   
  * ``tag-key`` - The key of a tag assigned to the resource. This filter is independent of the ``tag-value`` filter. For example, if you use both the filter "tag-key=Purpose" and the filter "tag-value=X", you get any resources assigned both the tag key Purpose (regardless of what the tag's value is), and the tag value X (regardless of what the tag's key is). If you want to list only resources where Purpose is X, see the ``tag`` :*key* =*value* filter. 
   
  * ``tag-value`` - The value of a tag assigned to the resource. This filter is independent of the ``tag-key`` filter. 
   
  * ``update-time`` - The time of the most recent update. 
   

  



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



``--next-token`` (string)


  The token to retrieve the next page of results.

  

``--max-results`` (integer)


  The maximum number of results to return in a single call.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

FpgaImages -> (list)

  

  Information about one or more FPGA images.

  

  (structure)

    

    Describes an Amazon FPGA image (AFI).

    

    FpgaImageId -> (string)

      

      The FPGA image identifier (AFI ID).

      

      

    FpgaImageGlobalId -> (string)

      

      The global FPGA image identifier (AGFI ID).

      

      

    Name -> (string)

      

      The name of the AFI.

      

      

    Description -> (string)

      

      The description of the AFI.

      

      

    ShellVersion -> (string)

      

      The version of the AWS Shell that was used to create the bitstream.

      

      

    PciId -> (structure)

      

      Information about the PCI bus.

      

      DeviceId -> (string)

        

        The ID of the device.

        

        

      VendorId -> (string)

        

        The ID of the vendor.

        

        

      SubsystemId -> (string)

        

        The ID of the subsystem.

        

        

      SubsystemVendorId -> (string)

        

        The ID of the vendor for the subsystem.

        

        

      

    State -> (structure)

      

      Information about the state of the AFI.

      

      Code -> (string)

        

        The state. The following are the possible values:

         

         
        * ``pending`` - AFI bitstream generation is in progress. 
         
        * ``available`` - The AFI is available for use. 
         
        * ``failed`` - AFI bitstream generation failed. 
         
        * ``unavailable`` - The AFI is no longer available for use. 
         

        

        

      Message -> (string)

        

        If the state is ``failed`` , this is the error message.

        

        

      

    CreateTime -> (timestamp)

      

      The date and time the AFI was created.

      

      

    UpdateTime -> (timestamp)

      

      The time of the most recent update to the AFI.

      

      

    OwnerId -> (string)

      

      The AWS account ID of the AFI owner.

      

      

    OwnerAlias -> (string)

      

      The alias of the AFI owner. Possible values include ``self`` , ``amazon`` , and ``aws-marketplace`` .

      

      

    ProductCodes -> (list)

      

      The product codes for the AFI.

      

      (structure)

        

        Describes a product code.

        

        ProductCodeId -> (string)

          

          The product code.

          

          

        ProductCodeType -> (string)

          

          The type of product code.

          

          

        

      

    Tags -> (list)

      

      Any tags assigned to the AFI.

      

      (structure)

        

        Describes a tag.

        

        Key -> (string)

          

          The key of the tag.

           

          Constraints: Tag keys are case-sensitive and accept a maximum of 127 Unicode characters. May not begin with ``aws:``  

          

          

        Value -> (string)

          

          The value of the tag.

           

          Constraints: Tag values are case-sensitive and accept a maximum of 255 Unicode characters.

          

          

        

      

    

  

NextToken -> (string)

  

  The token to use to retrieve the next page of results. This value is ``null`` when there are no more results to return.

  

  

