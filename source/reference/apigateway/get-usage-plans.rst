[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway get-usage-plans:


***************
get-usage-plans
***************



===========
Description
===========



Gets all the usage plans of the caller's account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/GetUsagePlans>`_


``get-usage-plans`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``items``


========
Synopsis
========

::

    get-usage-plans
  [--key-id <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--key-id`` (string)


  The identifier of the API key associated with the usage plans.

  

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

**To get the details of all Usage Plans**

Command::

  aws apigateway get-usage-plans


======
Output
======

position -> (string)

  

  

items -> (list)

  

  The current page of elements from this collection.

  

  (structure)

    

    Represents a usage plan than can specify who can assess associated API stages with specified request limits and quotas.

      

    In a usage plan, you associate an API by specifying the API's Id and a stage name of the specified API. You add plan customers by adding API keys to the plan. 

       `Create and Use Usage Plans <http://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-api-usage-plans.html>`_  

    id -> (string)

      

      The identifier of a  UsagePlan resource.

      

      

    name -> (string)

      

      The name of a usage plan.

      

      

    description -> (string)

      

      The description of a usage plan.

      

      

    apiStages -> (list)

      

      The associated API stages of a usage plan.

      

      (structure)

        

        API stage name of the associated API stage in a usage plan.

        

        apiId -> (string)

          

          API Id of the associated API stage in a usage plan.

          

          

        stage -> (string)

          

          API stage name of the associated API stage in a usage plan.

          

          

        

      

    throttle -> (structure)

      

      The request throttle limits of a usage plan.

      

      burstLimit -> (integer)

        

        The API request burst limit, the maximum rate limit over a time ranging from one to a few seconds, depending upon whether the underlying token bucket is at its full capacity.

        

        

      rateLimit -> (double)

        

        The API request steady-state rate limit.

        

        

      

    quota -> (structure)

      

      The maximum number of permitted requests per a given unit time interval.

      

      limit -> (integer)

        

        The maximum number of requests that can be made in a given time period.

        

        

      offset -> (integer)

        

        The number of requests subtracted from the given limit in the initial time period.

        

        

      period -> (string)

        

        The time period in which the limit applies. Valid values are "DAY", "WEEK" or "MONTH".

        

        

      

    productCode -> (string)

      

      The AWS Markeplace product identifier to associate with the usage plan as a SaaS product on AWS Marketplace.

      

      

    

  

