[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway get-api-keys:


************
get-api-keys
************



===========
Description
===========



Gets information about the current  ApiKeys resource.



``get-api-keys`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``items``


========
Synopsis
========

::

    get-api-keys
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

position -> (string)

  

  

items -> (list)

  

  The current page of any  ApiKey resources in the collection of  ApiKey resources.

  

  (structure)

    

    A resource that can be distributed to callers for executing  Method resources that require an API key. API keys can be mapped to any  Stage on any  RestApi , which indicates that the callers with the API key can make requests to that stage.

    

    id -> (string)

      

      The identifier of the API Key.

      

      

    name -> (string)

      

      The name of the API Key.

      

      

    description -> (string)

      

      The description of the API Key.

      

      

    enabled -> (boolean)

      

      Specifies whether the API Key can be used by callers.

      

      

    stageKeys -> (list)

      

      A list of  Stage resources that are associated with the  ApiKey resource.

      

      (string)

        

        

      

    createdDate -> (timestamp)

      

      The date when the API Key was created, in `ISO 8601 format`_ .

      

      

    lastUpdatedDate -> (timestamp)

      

      When the API Key was last updated, in ISO 8601 format.

      

      

    

  



.. _ISO 8601 format: http://www.iso.org/iso/home/standards/iso8601.htm
