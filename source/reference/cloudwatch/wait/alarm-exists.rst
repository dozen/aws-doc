[ :ref:`aws <cli:aws>` . :ref:`cloudwatch <cli:aws cloudwatch>` . :ref:`wait <cli:aws cloudwatch wait>` ]

.. _cli:aws cloudwatch wait alarm-exists:


************
alarm-exists
************



===========
Description
===========

Wait until JMESPath query length(MetricAlarms[]) > `0` returns True when polling with ``describe-alarms``. It will poll every 5 seconds until a successful state has been reached. This will exit with a return code of 255 after 40 failed checks.

See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/monitoring-2010-08-01/DescribeAlarms>`_


``alarm-exists`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``MetricAlarms``


========
Synopsis
========

::

    alarm-exists
  [--alarm-names <value>]
  [--alarm-name-prefix <value>]
  [--state-value <value>]
  [--action-prefix <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--alarm-names`` (list)


  The names of the alarms.

  



Syntax::

  "string" "string" ...



``--alarm-name-prefix`` (string)


  The alarm name prefix. If this parameter is specified, you cannot specify ``alarm-names`` .

  

``--state-value`` (string)


  The state value to be used in matching alarms.

  

  Possible values:

  
  *   ``OK``

  
  *   ``ALARM``

  
  *   ``INSUFFICIENT_DATA``

  

  

``--action-prefix`` (string)


  The action name prefix.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``next-token`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``next-token`` is provided in the command's output. To resume pagination, provide the ``next-token`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``next-token`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

None