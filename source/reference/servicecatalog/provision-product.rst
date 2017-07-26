[ :ref:`aws <cli:aws>` . :ref:`servicecatalog <cli:aws servicecatalog>` ]

.. _cli:aws servicecatalog provision-product:


*****************
provision-product
*****************



===========
Description
===========



Requests a *provision* of a specified product. A *provisioned product* is a resourced instance for a product. For example, provisioning a CloudFormation-template-backed product results in launching a CloudFormation stack and all the underlying resources that come with it. 

 

You can check the status of this request using the  describe-record operation. The error "Parameter validation failed: Missing required parameter in Tags[*N* ]:*Value* " indicates that your request contains a tag which has a tag key but no corresponding tag value (value is empty or null). Your call may have included values returned from a ``describe-provisioning-parameters`` call that resulted in a TagOption key with an empty list. This happens when TagOption keys are in conflict. For more information, see  describe-provisioning-parameters .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/servicecatalog-2015-12-10/ProvisionProduct>`_


========
Synopsis
========

::

    provision-product
  [--accept-language <value>]
  --product-id <value>
  --provisioning-artifact-id <value>
  [--path-id <value>]
  --provisioned-product-name <value>
  [--provisioning-parameters <value>]
  [--tags <value>]
  [--notification-arns <value>]
  --provision-token <value>
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

  

``--product-id`` (string)


  The product identifier.

  

``--provisioning-artifact-id`` (string)


  The provisioning artifact identifier for this product. This is sometimes referred to as the product version.

  

``--path-id`` (string)


  The identifier of the path for this product's provisioning. This value is optional if the product has a default path, and is required if there is more than one path for the specified product.

  

``--provisioned-product-name`` (string)


  A user-friendly name to identify the ProvisionedProduct object. This value must be unique for the AWS account and cannot be updated after the product is provisioned.

  

``--provisioning-parameters`` (list)


  Parameters specified by the administrator that are required for provisioning the product.

  



Shorthand Syntax::

    Key=string,Value=string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Value": "string"
    }
    ...
  ]



``--tags`` (list)


  A list of tags to use as provisioning options.

  



Shorthand Syntax::

    Key=string,Value=string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Value": "string"
    }
    ...
  ]



``--notification-arns`` (list)


  Passed to CloudFormation. The SNS topic ARNs to which to publish stack-related events.

  



Syntax::

  "string" "string" ...



``--provision-token`` (string)


  An idempotency token that uniquely identifies the provisioning request. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

RecordDetail -> (structure)

  

  The detailed result of the  provision-product request, containing the inputs made to that request, the current state of the request, a pointer to the ProvisionedProduct object of the request, and a list of any errors that the request encountered. 

  

  RecordId -> (string)

    

    The identifier of the ProvisionedProduct object record.

    

    

  ProvisionedProductName -> (string)

    

    The user-friendly name of the ProvisionedProduct object.

    

    

  Status -> (string)

    

    The status of the ProvisionedProduct object.

     

     ``CREATED`` - Request created but the operation has not yet started.

     

     ``IN_PROGRESS`` - The requested operation is in-progress.

     

     ``IN_PROGRESS_IN_ERROR`` - The provisioned product is under change but the requested operation failed and some remediation is occurring. For example, a rollback.

     

     ``SUCCEEDED`` - The requested operation has successfully completed.

     

     ``FAILED`` - The requested operation has completed but has failed. Investigate using the error messages returned.

    

    

  CreatedTime -> (timestamp)

    

    The UTC timestamp of the creation time.

    

    

  UpdatedTime -> (timestamp)

    

    The time when the record for the ProvisionedProduct object was last updated.

    

    

  ProvisionedProductType -> (string)

    

    The type of the ProvisionedProduct object.

    

    

  RecordType -> (string)

    

    The record type for this record.

    

    

  ProvisionedProductId -> (string)

    

    The identifier of the ProvisionedProduct object.

    

    

  ProductId -> (string)

    

    The product identifier.

    

    

  ProvisioningArtifactId -> (string)

    

    The provisioning artifact identifier for this product. This is sometimes referred to as the product version.

    

    

  PathId -> (string)

    

    The identifier of the path for this product's provisioning.

    

    

  RecordErrors -> (list)

    

    A list of errors that occurred while processing the request.

    

    (structure)

      

      The error code and description resulting from an operation.

      

      Code -> (string)

        

        The numeric value of the error.

        

        

      Description -> (string)

        

        The text description of the error.

        

        

      

    

  RecordTags -> (list)

    

    List of tags associated with this record.

    

    (structure)

      

      A tag associated with the record, stored as a key-value pair.

      

      Key -> (string)

        

        The key for this tag.

        

        

      Value -> (string)

        

        The value for this tag.

        

        

      

    

  

