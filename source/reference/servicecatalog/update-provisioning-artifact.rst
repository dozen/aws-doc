[ :ref:`aws <cli:aws>` . :ref:`servicecatalog <cli:aws servicecatalog>` ]

.. _cli:aws servicecatalog update-provisioning-artifact:


****************************
update-provisioning-artifact
****************************



===========
Description
===========



Updates an existing provisioning artifact's information. This operation does not work on a provisioning artifact associated with a product that has been shared with you.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/servicecatalog-2015-12-10/UpdateProvisioningArtifact>`_


========
Synopsis
========

::

    update-provisioning-artifact
  [--accept-language <value>]
  --product-id <value>
  --provisioning-artifact-id <value>
  [--name <value>]
  [--description <value>]
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


  The identifier of the provisioning artifact for the update request. This is sometimes referred to as the product version.

  

``--name`` (string)


  The updated name of the provisioning artifact.

  

``--description`` (string)


  The updated text description of the provisioning artifact.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ProvisioningArtifactDetail -> (structure)

  

  The resulting detailed provisioning artifact information.

  

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

    

    

  

Info -> (map)

  

  Additional information about the provisioning artifact update request.

  

  key -> (string)

    

    

  value -> (string)

    

    

  

Status -> (string)

  

  The status of the current request.

  

  

