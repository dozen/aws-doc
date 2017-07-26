[ :ref:`aws <cli:aws>` . :ref:`kinesis <cli:aws kinesis>` ]

.. _cli:aws kinesis list-streams:


************
list-streams
************



===========
Description
===========



Lists your streams.

 

The number of streams may be too large to return from a single call to ``list-streams`` . You can limit the number of returned streams using the ``Limit`` parameter. If you do not specify a value for the ``Limit`` parameter, Amazon Kinesis uses the default limit, which is currently 10.

 

You can detect if there are more streams available to list by using the ``HasMoreStreams`` flag from the returned output. If there are more streams available, you can request more streams by using the name of the last stream returned by the ``list-streams`` request in the ``ExclusiveStartStreamName`` parameter in a subsequent request to ``list-streams`` . The group of stream names returned by the subsequent request is then added to the list. You can continue this process until all the stream names have been collected in the list. 

 

 list-streams has a limit of 5 transactions per second per account.



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

StreamNames -> (list)

  

  The names of the streams that are associated with the AWS account making the ``list-streams`` request.

  

  (string)

    

    

  

HasMoreStreams -> (boolean)

  

  If set to ``true`` , there are more streams available to list.

  

  

