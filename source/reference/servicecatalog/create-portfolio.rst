[ :ref:`aws <cli:aws>` . :ref:`servicecatalog <cli:aws servicecatalog>` ]

.. _cli:aws servicecatalog create-portfolio:


****************
create-portfolio
****************



===========
Description
===========



Creates a new portfolio.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/servicecatalog-2015-12-10/CreatePortfolio>`_


========
Synopsis
========

::

    create-portfolio
  [--accept-language <value>]
  --display-name <value>
  [--description <value>]
  --provider-name <value>
  [--tags <value>]
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

  

``--display-name`` (string)


  The name to use for display purposes.

  

``--description`` (string)


  The text description of the portfolio.

  

``--provider-name`` (string)


  The name of the portfolio provider.

  

``--tags`` (list)


  Tags to associate with the new portfolio.

  



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



``--idempotency-token`` (string)


  A token to disambiguate duplicate requests. You can create multiple resources using the same input in multiple requests, provided that you also specify a different idempotency token for each request.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

PortfolioDetail -> (structure)

  

  The resulting detailed portfolio information.

  

  Id -> (string)

    

    The identifier for the portfolio.

    

    

  ARN -> (string)

    

    The ARN assigned to the portfolio.

    

    

  DisplayName -> (string)

    

    The name to use for display purposes.

    

    

  Description -> (string)

    

    The text description of the portfolio.

    

    

  CreatedTime -> (timestamp)

    

    The UTC timestamp of the creation time.

    

    

  ProviderName -> (string)

    

    The name of the portfolio provider.

    

    

  

Tags -> (list)

  

  Tags successfully associated with the new portfolio.

  

  (structure)

    

    Key-value pairs to associate with this provisioning. These tags are entirely discretionary and are propagated to the resources created in the provisioning.

    

    Key -> (string)

      

      The ``ProvisioningArtifactParameter.TagKey`` parameter from  describe-provisioning-parameters .

      

      

    Value -> (string)

      

      The desired value for this key.

      

      

    

  

