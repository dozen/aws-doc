[ :ref:`aws <cli:aws>` . :ref:`servicecatalog <cli:aws servicecatalog>` ]

.. _cli:aws servicecatalog search-products-as-admin:


************************
search-products-as-admin
************************



===========
Description
===========



Retrieves summary and status information about all products created within the caller's account. If a portfolio ID is provided, this operation retrieves information for only those products that are associated with the specified portfolio.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/servicecatalog-2015-12-10/SearchProductsAsAdmin>`_


========
Synopsis
========

::

    search-products-as-admin
  [--accept-language <value>]
  [--portfolio-id <value>]
  [--filters <value>]
  [--sort-by <value>]
  [--sort-order <value>]
  [--page-token <value>]
  [--page-size <value>]
  [--product-source <value>]
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

  

``--portfolio-id`` (string)


  The portfolio identifier.

  

``--filters`` (map)


  The list of filters with which to limit search results. If no search filters are specified, the output is all the products to which the administrator has access.

  



Shorthand Syntax::

    KeyName1=string,string,KeyName2=string,string
  
  Where valid key names are:
    FullTextSearch
    Owner
    ProductType
    SourceProductId




JSON Syntax::

  {"FullTextSearch"|"Owner"|"ProductType"|"SourceProductId": ["string", ...]
    ...}



``--sort-by`` (string)


  The sort field specifier. If no value is specified, results are not sorted.

  

  Possible values:

  
  *   ``Title``

  
  *   ``VersionCount``

  
  *   ``CreationDate``

  

  

``--sort-order`` (string)


  The sort order specifier. If no value is specified, results are not sorted.

  

  Possible values:

  
  *   ``ASCENDING``

  
  *   ``DESCENDING``

  

  

``--page-token`` (string)


  The page token of the first page retrieved. If null, this retrieves the first page of size ``page-size`` .

  

``--page-size`` (integer)


  The maximum number of items to return in the results. If more results exist than fit in the specified ``page-size`` , the value of ``NextPageToken`` in the response is non-null.

  

``--product-source`` (string)


  Access level of the source of the product.

  

  Possible values:

  
  *   ``ACCOUNT``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ProductViewDetails -> (list)

  

  List of detailed product view information objects.

  

  (structure)

    

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

      

      

    

  

NextPageToken -> (string)

  

  The page token to use to retrieve the next page of results for this operation. If there are no more pages, this value is null.

  

  

