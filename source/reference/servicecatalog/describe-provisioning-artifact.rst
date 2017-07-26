[ :ref:`aws <cli:aws>` . :ref:`servicecatalog <cli:aws servicecatalog>` ]

.. _cli:aws servicecatalog describe-provisioning-artifact:


******************************
describe-provisioning-artifact
******************************



===========
Description
===========



Retrieves detailed information about the specified provisioning artifact.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/servicecatalog-2015-12-10/DescribeProvisioningArtifact>`_


========
Synopsis
========

::

    describe-provisioning-artifact
  [--accept-language <value>]
  --provisioning-artifact-id <value>
  --product-id <value>
  [--verbose | --no-verbose]
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

  

``--provisioning-artifact-id`` (string)


  The identifier of the provisioning artifact. This is sometimes referred to as the product version.

  

``--product-id`` (string)


  The product identifier.

  

``--verbose`` | ``--no-verbose`` (boolean)


  Enable a verbose level of details for the provisioning artifact.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ProvisioningArtifactDetail -> (structure)

  

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

    

    

  

Info -> (map)

  

  Additional information about the provisioning artifact.

  

  key -> (string)

    

    

  value -> (string)

    

    

  

Status -> (string)

  

  The status of the current request.

  

  

