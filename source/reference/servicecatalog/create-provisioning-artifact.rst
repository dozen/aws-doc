[ :ref:`aws <cli:aws>` . :ref:`servicecatalog <cli:aws servicecatalog>` ]

.. _cli:aws servicecatalog create-provisioning-artifact:


****************************
create-provisioning-artifact
****************************



===========
Description
===========



Create a new provisioning artifact for the specified product. This operation does not work with a product that has been shared with you.

 

See the bottom of this topic for an example JSON request.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/servicecatalog-2015-12-10/CreateProvisioningArtifact>`_


========
Synopsis
========

::

    create-provisioning-artifact
  [--accept-language <value>]
  --product-id <value>
  --parameters <value>
  --idempotency-token <value>
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

  

``--parameters`` (structure)


  The parameters to use when creating the new provisioning artifact.

  



Shorthand Syntax::

    Name=string,Description=string,Info={KeyName1=string,KeyName2=string},Type=string




JSON Syntax::

  {
    "Name": "string",
    "Description": "string",
    "Info": {"string": "string"
      ...},
    "Type": "CLOUD_FORMATION_TEMPLATE"|"MARKETPLACE_AMI"|"MARKETPLACE_CAR"
  }



``--idempotency-token`` (string)


  A token to disambiguate duplicate requests. You can create multiple resources using the same input in multiple requests, provided that you also specify a different idempotency token for each request.

  

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

  

  Additional information about the creation request for the provisioning artifact.

  

  key -> (string)

    

    

  value -> (string)

    

    

  

Status -> (string)

  

  The status of the current request.

  

  

