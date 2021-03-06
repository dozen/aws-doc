[ :ref:`aws <cli:aws>` . :ref:`apigateway <cli:aws apigateway>` ]

.. _cli:aws apigateway get-usage:


*********
get-usage
*********



===========
Description
===========



Gets the usage data of a usage plan in a specified time interval.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/apigateway-2015-07-09/GetUsage>`_


``get-usage`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``items``


========
Synopsis
========

::

    get-usage
  --usage-plan-id <value>
  [--key-id <value>]
  --start-date <value>
  --end-date <value>
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--usage-plan-id`` (string)


  The Id of the usage plan associated with the usage data.

  

``--key-id`` (string)


  The Id of the API key associated with the resultant usage data.

  

``--start-date`` (string)


  The starting date (e.g., 2016-01-01) of the usage data.

  

``--end-date`` (string)


  The ending date (e.g., 2016-12-31) of the usage data.

  

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

**To get the usage details for a Usage Plan**

Command::

  aws apigateway get-usage --usage-plan-id a1b2c3 --start-date "2016-08-16" --end-date "2016-08-17"


======
Output
======

usagePlanId -> (string)

  

  The plan Id associated with this usage data.

  

  

startDate -> (string)

  

  The starting date of the usage data.

  

  

endDate -> (string)

  

  The ending date of the usage data.

  

  

position -> (string)

  

  

items -> (map)

  

  The usage data, as daily logs of used and remaining quotas, over the specified time interval indexed over the API keys in a usage plan. For example, ``{..., "values" : { "{api_key}" : [ [0, 100], [10, 90], [100, 10]]}`` , where ``{api_key}`` stands for an API key value and the daily log entry is of the format ``[used quota, remaining quota]`` .

  

  key -> (string)

    

    

  value -> (list)

    

    (list)

      

      (long)

        

        

      

    

  

