[ :ref:`aws <cli:aws>` . :ref:`servicecatalog <cli:aws servicecatalog>` ]

.. _cli:aws servicecatalog list-provisioning-artifacts:


***************************
list-provisioning-artifacts
***************************



===========
Description
===========



Lists all provisioning artifacts associated with the specified product.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/servicecatalog-2015-12-10/ListProvisioningArtifacts>`_


========
Synopsis
========

::

    list-provisioning-artifacts
  [--accept-language <value>]
  --product-id <value>
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

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ProvisioningArtifactDetails -> (list)

  

  List of detailed provisioning artifact information objects.

  

  (structure)

    

    Detailed provisioning artifact information.

    

    Id -> (string)

      

      The identifier of the provisioning artifact. This is sometimes referred to as the product version.

      

      

    Name -> (string)

      

      The name assigned to the provisioning artifact.

      

      

    Description -> (string)

      

      The text description of the provisioning artifact.

      

      

    Type -> (string)

      

      The type of the provisioning artifact. The following provisioning artifact types are used by AWS Marketplace products:

       

       ``MARKETPLACE_AMI`` - AMI products.

       

       ``MARKETPLACE_CAR`` - CAR (Cluster and AWS Resources) products.

      

      

    CreatedTime -> (timestamp)

      

      The UTC timestamp of the creation time.

      

      

    

  

NextPageToken -> (string)

  

  The page token to use to retrieve the next page of results for this operation. If there are no more pages, this value is null.

  

  

