[ :ref:`aws <cli:aws>` . :ref:`health <cli:aws health>` ]

.. _cli:aws health describe-event-types:


********************
describe-event-types
********************



===========
Description
===========



Returns the event types that meet the specified filter criteria. If no filter criteria are specified, all event types are returned, in no particular order.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/health-2016-08-04/DescribeEventTypes>`_


``describe-event-types`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``eventTypes``


========
Synopsis
========

::

    describe-event-types
  [--filter <value>]
  [--locale <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filter`` (structure)


  Values to narrow the results returned.

  



Shorthand Syntax::

    eventTypeCodes=string,string,services=string,string,eventTypeCategories=string,string




JSON Syntax::

  {
    "eventTypeCodes": ["string", ...],
    "services": ["string", ...],
    "eventTypeCategories": ["issue"|"accountNotification"|"scheduledChange", ...]
  }



``--locale`` (string)


  The locale (language) to return information in. English (en) is the default and the only supported value at this time.

  

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



======
Output
======

eventTypes -> (list)

  

  A list of event types that match the filter criteria. Event types have a category (``issue`` , ``accountNotification`` , or ``scheduledChange`` ), a service (for example, ``EC2`` , ``RDS`` , ``DATAPIPELINE`` , ``BILLING`` ), and a code (in the format ``AWS_*SERVICE* _*DESCRIPTION* `` ; for example, ``AWS_EC2_SYSTEM_MAINTENANCE_EVENT`` ).

  

  (structure)

    

    Metadata about a type of event that is reported by AWS Health. Data consists of the category (for example, ``issue`` ), the service (for example, ``EC2`` ), and the event type code (for example, ``AWS_EC2_SYSTEM_MAINTENANCE_EVENT`` ).

    

    service -> (string)

      

      The AWS service that is affected by the event. For example, ``EC2`` , ``RDS`` .

      

      

    code -> (string)

      

      The unique identifier for the event type. The format is ``AWS_*SERVICE* _*DESCRIPTION* `` ; for example, ``AWS_EC2_SYSTEM_MAINTENANCE_EVENT`` .

      

      

    category -> (string)

      

      A list of event type category codes (``issue`` , ``scheduledChange`` , or ``accountNotification`` ).

      

      

    

  

nextToken -> (string)

  

  If the results of a search are large, only a portion of the results are returned, and a ``next-token`` pagination token is returned in the response. To retrieve the next batch of results, reissue the search request and include the returned token. When all results have been returned, the response does not contain a pagination token value.

  

  

