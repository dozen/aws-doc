[ :ref:`aws <cli:aws>` . :ref:`servicecatalog <cli:aws servicecatalog>` ]

.. _cli:aws servicecatalog terminate-provisioned-product:


*****************************
terminate-provisioned-product
*****************************



===========
Description
===========



Requests termination of an existing ProvisionedProduct object. If there are ``Tags`` associated with the object, they are terminated when the ProvisionedProduct object is terminated. 

 

This operation does not delete any records associated with the ProvisionedProduct object.

 

You can check the status of this request using the  describe-record operation.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/servicecatalog-2015-12-10/TerminateProvisionedProduct>`_


========
Synopsis
========

::

    terminate-provisioned-product
  [--provisioned-product-name <value>]
  [--provisioned-product-id <value>]
  --terminate-token <value>
  [--ignore-errors | --no-ignore-errors]
  [--accept-language <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--provisioned-product-name`` (string)


  The name of the ProvisionedProduct object to terminate. Specify either ``ProvisionedProductName`` or ``ProvisionedProductId`` , but not both.

  

``--provisioned-product-id`` (string)


  The identifier of the ProvisionedProduct object to terminate. Specify either ``ProvisionedProductName`` or ``ProvisionedProductId`` , but not both.

  

``--terminate-token`` (string)


  An idempotency token that uniquely identifies the termination request. This token is only valid during the termination process. After the ProvisionedProduct object is terminated, further requests to terminate the same ProvisionedProduct object always return **ResourceNotFound** regardless of the value of ``TerminateToken`` .

  

``--ignore-errors`` | ``--no-ignore-errors`` (boolean)


  If set to true, AWS Service Catalog stops managing the specified ProvisionedProduct object even if it cannot delete the underlying resources.

  

``--accept-language`` (string)


  The language code to use for this operation. Supported language codes are as follows:

   

  "en" (English)

   

  "jp" (Japanese)

   

  "zh" (Chinese)

   

  If no code is specified, "en" is used as the default.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

RecordDetail -> (structure)

  

  The detailed result of the  terminate-provisioned-product request, containing the inputs made to that request, the current state of the request, a pointer to the ProvisionedProduct object that the request is modifying, and a list of any errors that the request encountered.

  

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

        

        

      

    

  

