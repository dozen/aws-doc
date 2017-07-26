[ :ref:`aws <cli:aws>` . :ref:`kinesis <cli:aws kinesis>` ]

.. _cli:aws kinesis list-streams:


************
list-streams
************



===========
Description
===========



Lists your Amazon Kinesis streams.

 

The number of streams may be too large to return from a single call to ``list-streams`` . You can limit the number of returned streams using the ``Limit`` parameter. If you do not specify a value for the ``Limit`` parameter, Amazon Kinesis uses the default limit, which is currently 10.

 

You can detect if there are more streams available to list by using the ``HasMoreStreams`` flag from the returned output. If there are more streams available, you can request more streams by using the name of the last stream returned by the ``list-streams`` request in the ``ExclusiveStartStreamName`` parameter in a subsequent request to ``list-streams`` . The group of stream names returned by the subsequent request is then added to the list. You can continue this process until all the stream names have been collected in the list. 

 

  list-streams has a limit of 5 transactions per second per account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/kinesis-2013-12-02/ListStreams>`_


``list-streams`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``StreamNames``


========
Synopsis
========

::

    list-streams
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

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

StreamNames -> (list)

  

  The names of the streams that are associated with the AWS account making the ``list-streams`` request.

  

  (string)

    

    

  

HasMoreStreams -> (boolean)

  

  If set to ``true`` , there are more streams available to list.

  

  

