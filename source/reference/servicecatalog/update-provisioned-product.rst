[ :ref:`aws <cli:aws>` . :ref:`servicecatalog <cli:aws servicecatalog>` ]

.. _cli:aws servicecatalog update-provisioned-product:


**************************
update-provisioned-product
**************************



===========
Description
===========



Requests updates to the configuration of an existing ProvisionedProduct object. If there are tags associated with the object, they cannot be updated or added with this operation. Depending on the specific updates requested, this operation may update with no interruption, with some interruption, or replace the ProvisionedProduct object entirely. 

 

You can check the status of this request using the  describe-record operation.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/servicecatalog-2015-12-10/UpdateProvisionedProduct>`_


========
Synopsis
========

::

    update-provisioned-product
  [--accept-language <value>]
  [--provisioned-product-name <value>]
  [--provisioned-product-id <value>]
  [--product-id <value>]
  [--provisioning-artifact-id <value>]
  [--path-id <value>]
  [--provisioning-parameters <value>]
  --update-token <value>
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

  

``--provisioned-product-name`` (string)


  The updated name of the ProvisionedProduct object. Specify either ``ProvisionedProductName`` or ``ProvisionedProductId`` , but not both.

  

``--provisioned-product-id`` (string)


  The identifier of the ProvisionedProduct object to update. Specify either ``ProvisionedProductName`` or ``ProvisionedProductId`` , but not both.

  

``--product-id`` (string)


  The identifier of the ProvisionedProduct object.

  

``--provisioning-artifact-id`` (string)


  The provisioning artifact identifier for this product. This is sometimes referred to as the product version.

  

``--path-id`` (string)


  The identifier of the path to use in the updated ProvisionedProduct object. This value is optional if the product has a default path, and is required if there is more than one path for the specified product.

  

``--provisioning-parameters`` (list)


  A list of ``ProvisioningParameter`` objects used to update the ProvisionedProduct object.

  



Shorthand Syntax::

    Key=string,Value=string,UsePreviousValue=boolean ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Value": "string",
      "UsePreviousValue": true|false
    }
    ...
  ]



``--update-token`` (string)


  The idempotency token that uniquely identifies the provisioning update request.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

RecordDetail -> (structure)

  

  The detailed result of the  update-provisioned-product request, containing the inputs made to that request, the current state of the request, a pointer to the ProvisionedProduct object that the request is modifying, and a list of any errors that the request encountered.

  

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

        

        

      

    

  

