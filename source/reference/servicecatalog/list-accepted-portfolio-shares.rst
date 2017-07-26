[ :ref:`aws <cli:aws>` . :ref:`servicecatalog <cli:aws servicecatalog>` ]

.. _cli:aws servicecatalog list-accepted-portfolio-shares:


******************************
list-accepted-portfolio-shares
******************************



===========
Description
===========



Lists details of all portfolios for which sharing was accepted by this account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/servicecatalog-2015-12-10/ListAcceptedPortfolioShares>`_


========
Synopsis
========

::

    list-accepted-portfolio-shares
  [--accept-language <value>]
  [--page-token <value>]
  [--page-size <value>]
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

  

``--page-token`` (string)


  The page token of the first page retrieved. If null, this retrieves the first page of size ``page-size`` .

  

``--page-size`` (integer)


  The maximum number of items to return in the results. If more results exist than fit in the specified ``page-size`` , the value of ``NextPageToken`` in the response is non-null.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

PortfolioDetails -> (list)

  

  List of detailed portfolio information objects.

  

  (structure)

    

    Detailed portfolio information.

    

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

      

      

    

  

NextPageToken -> (string)

  

  The page token to use to retrieve the next page of results for this operation. If there are no more pages, this value is null.

  

  

