[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway get-api-keys:


************
get-api-keys
************



===========
Description
===========



Gets information about the current  ApiKeys resource.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/GetApiKeys>`_


``get-api-keys`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``items``


========
Synopsis
========

::

    get-api-keys
  [--name-query <value>]
  [--customer-id <value>]
  [--include-values | --no-include-values]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name-query`` (string)


  The name of queried API keys.

  

``--customer-id`` (string)


  The identifier of a customer in AWS Marketplace or an external system, such as a developer portal.

  

``--include-values`` | ``--no-include-values`` (boolean)


  A boolean flag to specify whether (``true`` ) or not (``false`` ) the result contains key values.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get the list of API keys**

Command::

  aws apigateway get-api-keys

Output::

  {
      "items": [
          {
              "description": "My first key", 
              "enabled": true, 
              "stageKeys": [
                  "a1b2c3d4e5/dev", 
                  "e5d4c3b2a1/dev"
              ], 
              "lastUpdatedDate": 1456184515, 
              "createdDate": 1456184452, 
              "id": "8bklk8bl1k3sB38D9B3l0enyWT8c09B30lkq0blk", 
              "name": "My key"
          }
      ]
  }


======
Output
======

warnings -> (list)

  

  A list of warning messages logged during the import of API keys when the ``failOnWarnings`` option is set to true.

  

  (string)

    

    

  

position -> (string)

  

  

items -> (list)

  

  The current page of elements from this collection.

  

  (structure)

    

    A resource that can be distributed to callers for executing  Method resources that require an API key. API keys can be mapped to any  Stage on any  RestApi , which indicates that the callers with the API key can make requests to that stage.

      `Use API Keys <http://docs.aws.amazon.com/apigateway/latest/developerguide/how-to-api-keys.html>`_  

    id -> (string)

      

      The identifier of the API Key.

      

      

    value -> (string)

      

      The value of the API Key.

      

      

    name -> (string)

      

      The name of the API Key.

      

      

    customerId -> (string)

      

      An AWS Marketplace customer identifier , when integrating with the AWS SaaS Marketplace.

      

      

    description -> (string)

      

      The description of the API Key.

      

      

    enabled -> (boolean)

      

      Specifies whether the API Key can be used by callers.

      

      

    createdDate -> (timestamp)

      

      The timestamp when the API Key was created.

      

      

    lastUpdatedDate -> (timestamp)

      

      The timestamp when the API Key was last updated.

      

      

    stageKeys -> (list)

      

      A list of  Stage resources that are associated with the  ApiKey resource.

      

      (string)

        

        

      

    

  

