[ :ref:`aws <cli:aws>` . :ref:`health <cli:aws health>` ]

.. _cli:aws health describe-affected-entities:


**************************
describe-affected-entities
**************************



===========
Description
===========



Returns a list of entities that have been affected by the specified events, based on the specified filter criteria. Entities can refer to individual customer resources, groups of customer resources, or any other construct, depending on the AWS service. Events that have impact beyond that of the affected entities, or where the extent of impact is unknown, include at least one entity indicating this.

 

At least one event ARN is required. Results are sorted by the ``lastUpdatedTime`` of the entity, starting with the most recent.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/health-2016-08-04/DescribeAffectedEntities>`_


``describe-affected-entities`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``entities``


========
Synopsis
========

::

    describe-affected-entities
  --filter <value>
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


  Values to narrow the results returned. At least one event ARN is required. 

  



Shorthand Syntax::

    eventArns=string,string,entityArns=string,string,entityValues=string,string,lastUpdatedTimes=[{from=timestamp,to=timestamp},{from=timestamp,to=timestamp}],tags=[{KeyName1=string,KeyName2=string},{KeyName1=string,KeyName2=string}],statusCodes=string,string




JSON Syntax::

  {
    "eventArns": ["string", ...],
    "entityArns": ["string", ...],
    "entityValues": ["string", ...],
    "lastUpdatedTimes": [
      {
        "from": timestamp,
        "to": timestamp
      }
      ...
    ],
    "tags": [
      {"string": "string"
        ...}
      ...
    ],
    "statusCodes": ["IMPAIRED"|"UNIMPAIRED"|"UNKNOWN", ...]
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

entities -> (list)

  

  The entities that match the filter criteria.

  

  (structure)

    

    Information about an entity that is affected by a Health event.

    

    entityArn -> (string)

      

      The unique identifier for the entity. Format: ``arn:aws:health:*entity-region* :*aws-account* :entity/*entity-id* `` . Example: ``arn:aws:health:us-east-1:111222333444:entity/AVh5GGT7ul1arKr1sE1K``  

      

      

    eventArn -> (string)

      

      The unique identifier for the event. Format: ``arn:aws:health:*event-region* ::event/*EVENT_TYPE_PLUS_ID* `` . Example: ``arn:aws:health:us-east-1::event/AWS_EC2_MAINTENANCE_5331``  

      

      

    entityValue -> (string)

      

      The ID of the affected entity.

      

      

    awsAccountId -> (string)

      

      The 12-digit AWS account number that contains the affected entity.

      

      

    lastUpdatedTime -> (timestamp)

      

      The most recent time that the entity was updated.

      

      

    statusCode -> (string)

      

      The most recent status of the entity affected by the event. The possible values are ``IMPAIRED`` , ``UNIMPAIRED`` , and ``UNKNOWN`` .

      

      

    tags -> (map)

      

      A map of entity tags attached to the affected entity.

      

      key -> (string)

        

        

      value -> (string)

        

        

      

    

  

nextToken -> (string)

  

  If the results of a search are large, only a portion of the results are returned, and a ``next-token`` pagination token is returned in the response. To retrieve the next batch of results, reissue the search request and include the returned token. When all results have been returned, the response does not contain a pagination token value.

  

  

