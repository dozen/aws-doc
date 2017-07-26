[ :ref:`aws <cli:aws>` . :ref:`servicecatalog <cli:aws servicecatalog>` ]

.. _cli:aws servicecatalog describe-product:


****************
describe-product
****************



===========
Description
===========



Retrieves information about a specified product.

 

This operation is functionally identical to  describe-product-view except that it takes as input ``ProductId`` instead of ``ProductViewId`` .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/servicecatalog-2015-12-10/DescribeProduct>`_


========
Synopsis
========

::

    describe-product
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


  The ``ProductId`` of the product to describe.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ProductViewSummary -> (structure)

  

  The summary metadata about the specified product.

  

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

    

    

  

ProvisioningArtifacts -> (list)

  

  A list of provisioning artifact objects for the specified product. The ``ProvisioningArtifacts`` parameter represent the ways the specified product can be provisioned.

  

  (structure)

    

    Contains information indicating the ways in which a product can be provisioned.

    

    Id -> (string)

      

      The identifier for the artifact. This is sometimes referred to as the product version.

      

      

    Name -> (string)

      

      The name of the artifact.

      

      

    Description -> (string)

      

      The text description of the artifact.

      

      

    CreatedTime -> (timestamp)

      

      The UTC timestamp of the creation time.

      

      

    

  

