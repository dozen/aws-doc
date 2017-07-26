[ :ref:`aws <cli:aws>` . :ref:`servicecatalog <cli:aws servicecatalog>` ]

.. _cli:aws servicecatalog describe-provisioning-parameters:


********************************
describe-provisioning-parameters
********************************



===========
Description
===========



Provides information about parameters required to provision a specified product in a specified manner. Use this operation to obtain the list of ``ProvisioningArtifactParameters`` parameters available to call the  provision-product operation for the specified product.

 

If the output contains a TagOption key with an empty list of values, there is a TagOption conflict for that key. The end user cannot take action to fix the conflict, and launch is not blocked. In subsequent calls to the ``provision-product`` operation, do not include conflicted TagOption keys as tags. Calls to ``provision-product`` with empty TagOption values cause the error "Parameter validation failed: Missing required parameter in Tags[*N* ]:*Value* ". Calls to ``provision-product`` with conflicted TagOption keys automatically tag the provisioned product with the conflicted keys with the value "``sc-tagoption-conflict-portfolioId-productId`` ".



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/servicecatalog-2015-12-10/DescribeProvisioningParameters>`_


========
Synopsis
========

::

    describe-provisioning-parameters
  [--accept-language <value>]
  --product-id <value>
  --provisioning-artifact-id <value>
  [--path-id <value>]
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

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ProvisioningArtifactParameters -> (list)

  

  The list of parameters used to successfully provision the product. Each parameter includes a list of allowable values and additional metadata about each parameter.

  

  (structure)

    

    A parameter used to successfully provision the product. This value includes a list of allowable values and additional metadata. 

    

    ParameterKey -> (string)

      

      The parameter key. 

      

      

    DefaultValue -> (string)

      

      The default value for this parameter.

      

      

    ParameterType -> (string)

      

      The parameter type.

      

      

    IsNoEcho -> (boolean)

      

      If this value is true, the value for this parameter is obfuscated from view when the parameter is retrieved. This parameter is used to hide sensitive information.

      

      

    Description -> (string)

      

      The text description of the parameter.

      

      

    ParameterConstraints -> (structure)

      

      The list of constraints that the administrator has put on the parameter.

      

      AllowedValues -> (list)

        

        The values that the administrator has allowed for the parameter.

        

        (string)

          

          

        

      

    

  

ConstraintSummaries -> (list)

  

  The list of constraint summaries that apply to provisioning this product.

  

  (structure)

    

    An administrator-specified constraint to apply when provisioning a product.

    

    Type -> (string)

      

      The type of the constraint. 

      

      

    Description -> (string)

      

      The text description of the constraint.

      

      

    

  

UsageInstructions -> (list)

  

  Any additional metadata specifically related to the provisioning of the product. For example, see the ``Version`` field of the CloudFormation template.

  

  (structure)

    

    Additional information provided by the administrator.

    

    Type -> (string)

      

      The usage instruction type for the value.

      

      

    Value -> (string)

      

      The usage instruction value for this type.

      

      

    

  

TagOptions -> (list)

  

  List of TagOptions associated with the provisioned provisioning parameters.

  

  (structure)

    

    The TagOption summary key-value pair.

    

    Key -> (string)

      

      The TagOptionSummary key.

      

      

    Values -> (list)

      

      The TagOptionSummary value.

      

      (string)

        

        

      

    

  

