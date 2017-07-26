[ :ref:`aws <cli:aws>` . :ref:`servicecatalog <cli:aws servicecatalog>` ]

.. _cli:aws servicecatalog describe-product-as-admin:


*************************
describe-product-as-admin
*************************



===========
Description
===========



Retrieves information about a specified product, run with administrator access.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/servicecatalog-2015-12-10/DescribeProductAsAdmin>`_


========
Synopsis
========

::

    describe-product-as-admin
  [--accept-language <value>]
  --id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--accept-language`` (string)


  The language code to use for this operation. Supported language codes are as follows:

   

  "en" (English)

   

  "jp" (Japanese)

   

  "zh" (Chinese)

   

  If no code is specified, "en" is used as the default.

  

``--id`` (string)


  The identifier of the product for which to retrieve information.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ProductViewDetail -> (structure)

  

  Detailed product view information.

  

  ProductViewSummary -> (structure)

    

    The summary metadata about the specified product view.

    

    Id -> (string)

      

      The product view identifier.

      

      

    ProductId -> (string)

      

      The product identifier.

      

      

    Name -> (string)

      

      The name of the product.

      

      

    Owner -> (string)

      

      The owner of the product. Contact the product administrator for the significance of this value.

      

      

    ShortDescription -> (string)

      

      Short description of the product.

      

      

    Type -> (string)

      

      The product type. Contact the product administrator for the significance of this value. If this value is ``MARKETPLACE`` , the product was created by AWS Marketplace.

      

      

    Distributor -> (string)

      

      The distributor of the product. Contact the product administrator for the significance of this value.

      

      

    HasDefaultPath -> (boolean)

      

      A value of ``false`` indicates that the product does not have a default path, while a value of ``true`` indicates that it does. If it's false, call  list-launch-paths to disambiguate between paths. If true,  list-launch-paths is not required, and the output of the  ProductViewSummary operation can be used directly with  describe-provisioning-parameters .

      

      

    SupportEmail -> (string)

      

      The email contact information to obtain support for this Product.

      

      

    SupportDescription -> (string)

      

      The description of the support for this Product.

      

      

    SupportUrl -> (string)

      

      The URL information to obtain support for this Product.

      

      

    

  Status -> (string)

    

    Current status of the product.

     

     ``AVAILABLE`` - Product is available for use.

     

     ``CREATING`` - Creation of product started, not ready for use.

     

     ``FAILED`` - Action on product failed.

    

    

  ProductARN -> (string)

    

    The ARN associated with the product.

    

    

  CreatedTime -> (timestamp)

    

    The UTC timestamp of the creation time.

    

    

  

ProvisioningArtifactSummaries -> (list)

  

  A list of provisioning artifact summaries for the product.

  

  (structure)

    

    Stores summary information about a provisioning artifact.

    

    Id -> (string)

      

      The identifier of the provisioning artifact.

      

      

    Name -> (string)

      

      The name of the provisioning artifact.

      

      

    Description -> (string)

      

      The description of the provisioning artifact.

      

      

    CreatedTime -> (timestamp)

      

      The UTC timestamp of the creation time.

      

      

    ProvisioningArtifactMetadata -> (map)

      

      The provisioning artifact metadata. This data is used with products created by AWS Marketplace.

      

      key -> (string)

        

        

      value -> (string)

        

        

      

    

  

Tags -> (list)

  

  Tags associated with the product.

  

  (structure)

    

    Key-value pairs to associate with this provisioning. These tags are entirely discretionary and are propagated to the resources created in the provisioning.

    

    Key -> (string)

      

      The ``ProvisioningArtifactParameter.TagKey`` parameter from  describe-provisioning-parameters .

      

      

    Value -> (string)

      

      The desired value for this key.

      

      

    

  

TagOptions -> (list)

  

  List of TagOptions associated with the product.

  

  (structure)

    

    The TagOption details.

    

    Key -> (string)

      

      The TagOptionDetail key.

      

      

    Value -> (string)

      

      The TagOptionDetail value.

      

      

    Active -> (boolean)

      

      The TagOptionDetail active state.

      

      

    Id -> (string)

      

      The TagOptionDetail identifier.

      

      

    

  

