[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway get-usage-plan-keys:


*******************
get-usage-plan-keys
*******************



===========
Description
===========



Gets all the usage plan keys representing the API keys added to a specified usage plan.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/GetUsagePlanKeys>`_


``get-usage-plan-keys`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``items``


========
Synopsis
========

::

    get-usage-plan-keys
  --usage-plan-id <value>
  [--name-query <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--usage-plan-id`` (string)


  The Id of the  UsagePlan resource representing the usage plan containing the to-be-retrieved  UsagePlanKey resource representing a plan customer.

  

``--name-query`` (string)


  A query parameter specifying the name of the to-be-returned usage plan keys.

  

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

**To get the list of API keys associated with a Usage Plan**

Command::

  aws apigateway get-usage-plan-keys --usage-plan-id a1b2c3


======
Output
======

position -> (string)

  

  

items -> (list)

  

  The current page of elements from this collection.

  

  (structure)

    

    Represents a usage plan key to identify a plan customer.

      

    To associate an API stage with a selected API key in a usage plan, you must create a UsagePlanKey resource to represent the selected  ApiKey .

     "  `Create and Use Usage Plans <http://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-api-usage-plans.html>`_  

    id -> (string)

      

      The Id of a usage plan key.

      

      

    type -> (string)

      

      The type of a usage plan key. Currently, the valid key type is ``API_KEY`` .

      

      

    value -> (string)

      

      The value of a usage plan key.

      

      

    name -> (string)

      

      The name of a usage plan key.

      

      

    

  

