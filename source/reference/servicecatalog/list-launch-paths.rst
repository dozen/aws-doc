[ :ref:`aws <cli:aws>` . :ref:`servicecatalog <cli:aws servicecatalog>` ]

.. _cli:aws servicecatalog list-launch-paths:


*****************
list-launch-paths
*****************



===========
Description
===========



Returns a paginated list of all paths to a specified product. A path is how the user has access to a specified product, and is necessary when provisioning a product. A path also determines the constraints put on the product.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/servicecatalog-2015-12-10/ListLaunchPaths>`_


========
Synopsis
========

::

    list-launch-paths
  [--accept-language <value>]
  --product-id <value>
  [--page-size <value>]
  [--page-token <value>]
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


  The product identifier. Identifies the product for which to retrieve ``LaunchPathSummaries`` information.

  

``--page-size`` (integer)


  The maximum number of items to return in the results. If more results exist than fit in the specified ``page-size`` , the value of ``NextPageToken`` in the response is non-null.

  

``--page-token`` (string)


  The page token of the first page retrieved. If null, this retrieves the first page of size ``page-size`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

LaunchPathSummaries -> (list)

  

  List of launch path information summaries for the specified ``page-token`` .

  

  (structure)

    

    Summary information about a path for a user to have access to a specified product.

    

    Id -> (string)

      

      The unique identifier of the product path.

      

      

    ConstraintSummaries -> (list)

      

      List of constraints on the portfolio-product relationship.

      

      (structure)

        

        An administrator-specified constraint to apply when provisioning a product.

        

        Type -> (string)

          

          The type of the constraint. 

          

          

        Description -> (string)

          

          The text description of the constraint.

          

          

        

      

    Tags -> (list)

      

      List of tags used by this launch path.

      

      (structure)

        

        Key-value pairs to associate with this provisioning. These tags are entirely discretionary and are propagated to the resources created in the provisioning.

        

        Key -> (string)

          

          The ``ProvisioningArtifactParameter.TagKey`` parameter from  describe-provisioning-parameters .

          

          

        Value -> (string)

          

          The desired value for this key.

          

          

        

      

    Name -> (string)

      

      Corresponds to the name of the portfolio to which the user was assigned.

      

      

    

  

NextPageToken -> (string)

  

  The page token to use to retrieve the next page of results for this operation. If there are no more pages, this value is null.

  

  

