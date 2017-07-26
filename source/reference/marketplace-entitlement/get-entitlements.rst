[ :ref:`aws <cli:aws>` . :ref:`marketplace-entitlement <cli:aws marketplace-entitlement>` ]

.. _cli:aws marketplace-entitlement get-entitlements:


****************
get-entitlements
****************



===========
Description
===========



get-entitlements retrieves entitlement values for a given product. The results can be filtered based on customer identifier or product dimensions.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/entitlement.marketplace-2017-01-11/GetEntitlements>`_


========
Synopsis
========

::

    get-entitlements
  --product-code <value>
  [--filter <value>]
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--product-code`` (string)


  Product code is used to uniquely identify a product in AWS Marketplace. The product code will be provided by AWS Marketplace when the product listing is created.

  

``--filter`` (map)


  Filter is used to return entitlements for a specific customer or for a specific dimension. Filters are described as keys mapped to a lists of values. Filtered requests are *unioned* for each value in the value list, and then *intersected* for each filter key.

  



Shorthand Syntax::

    KeyName1=string,string,KeyName2=string,string
  
  Where valid key names are:
    CUSTOMER_IDENTIFIER
    DIMENSION




JSON Syntax::

  {"CUSTOMER_IDENTIFIER"|"DIMENSION": ["string", ...]
    ...}



``--next-token`` (string)


  For paginated calls to GetEntitlements, pass the NextToken from the previous GetEntitlementsResult.

  

``--max-results`` (integer)


  The maximum number of items to retrieve from the get-entitlements operation. For pagination, use the NextToken field in subsequent calls to GetEntitlements.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Entitlements -> (list)

  

  The set of entitlements found through the get-entitlements operation. If the result contains an empty set of entitlements, NextToken might still be present and should be used.

  

  (structure)

    

    An entitlement represents capacity in a product owned by the customer. For example, a customer might own some number of users or seats in an SaaS application or some amount of data capacity in a multi-tenant database.

    

    ProductCode -> (string)

      

      The product code for which the given entitlement applies. Product codes are provided by AWS Marketplace when the product listing is created.

      

      

    Dimension -> (string)

      

      The dimension for which the given entitlement applies. Dimensions represent categories of capacity in a product and are specified when the product is listed in AWS Marketplace.

      

      

    CustomerIdentifier -> (string)

      

      The customer identifier is a handle to each unique customer in an application. Customer identifiers are obtained through the ResolveCustomer operation in AWS Marketplace Metering Service.

      

      

    Value -> (structure)

      

      The EntitlementValue represents the amount of capacity that the customer is entitled to for the product.

      

      IntegerValue -> (integer)

        

        The IntegerValue field will be populated with an integer value when the entitlement is an integer type. Otherwise, the field will not be set.

        

        

      DoubleValue -> (double)

        

        The DoubleValue field will be populated with a double value when the entitlement is a double type. Otherwise, the field will not be set.

        

        

      BooleanValue -> (boolean)

        

        The BooleanValue field will be populated with a boolean value when the entitlement is a boolean type. Otherwise, the field will not be set.

        

        

      StringValue -> (string)

        

        The StringValue field will be populated with a string value when the entitlement is a string type. Otherwise, the field will not be set.

        

        

      

    ExpirationDate -> (timestamp)

      

      The expiration date represents the minimum date through which this entitlement is expected to remain valid. For contractual products listed on AWS Marketplace, the expiration date is the date at which the customer will renew or cancel their contract. Customers who are opting to renew their contract will still have entitlements with an expiration date.

      

      

    

  

NextToken -> (string)

  

  For paginated results, use NextToken in subsequent calls to GetEntitlements. If the result contains an empty set of entitlements, NextToken might still be present and should be used.

  

  

