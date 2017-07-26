[ :ref:`aws <cli:aws>` . :ref:`opsworkscm <cli:aws opsworkscm>` ]

.. _cli:aws opsworkscm describe-events:


***************
describe-events
***************



===========
Description
===========



Describes events for a specified server. Results are ordered by time, with newest events first. 

 

This operation is synchronous. 

 

A ``ResourceNotFoundException`` is thrown when the server does not exist. A ``ValidationException`` is raised when parameters of the request are not valid. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/opsworkscm-2016-11-01/DescribeEvents>`_


========
Synopsis
========

::

    describe-events
  --server-name <value>
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--server-name`` (string)


  The name of the server for which you want to view events.

  

``--next-token`` (string)


  next-token is a string that is returned in some command responses. It indicates that not all entries have been returned, and that you must run at least one more request to get remaining items. To get remaining results, call ``describe-events`` again, and assign the token from the previous results as the value of the ``nextToken`` parameter. If there are no more results, the response object's ``nextToken`` parameter value is ``null`` . Setting a ``nextToken`` value that was not returned in your previous results causes an ``InvalidNextTokenException`` to occur. 

  

``--max-results`` (integer)


  To receive a paginated response, use this parameter to specify the maximum number of results to be returned with a single call. If the number of available results exceeds this maximum, the response includes a ``next-token`` value that you can assign to the ``next-token`` request parameter to get the next set of results. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe events**

The following ``describe-events`` command returns information about all events
that are associated with a Chef Automate server named ``automate-06``.::

  aws opsworks-cm describe-events --server-name 'automate-06'

The output for each event entry returned by the command resembles the following.
*Output*::

  {
   "ServerEvents": [ 
      { 
         "CreatedAt": 2016-07-29T13:38:47.520Z,
         "LogUrl": "https://s3.amazonaws.com/automate-06/automate-06-20160729133847520",
         "Message": "Updates successfully installed.",
         "ServerName": "automate-06"
      }
   ]
}

**More Information**

For more information, see `General Troubleshooting Tips`_ in the *AWS OpsWorks User Guide*.

.. _`General Troubleshooting Tips`: http://docs.aws.amazon.com/opsworks/latest/userguide/troubleshoot-opscm.html#d0e4561



======
Output
======

ServerEvents -> (list)

  

  Contains the response to a ``describe-events`` request. 

  

  (structure)

    

    An event that is related to the server, such as the start of maintenance or backup. 

    

    CreatedAt -> (timestamp)

      

      The time when the event occurred. 

      

      

    ServerName -> (string)

      

      The name of the server on or for which the event occurred. 

      

      

    Message -> (string)

      

      A human-readable informational or status message.

      

      

    LogUrl -> (string)

      

      The Amazon S3 URL of the event's log file.

      

      

    

  

NextToken -> (string)

  

  next-token is a string that is returned in some command responses. It indicates that not all entries have been returned, and that you must run at least one more request to get remaining items. To get remaining results, call ``describe-events`` again, and assign the token from the previous results as the value of the ``nextToken`` parameter. If there are no more results, the response object's ``nextToken`` parameter value is ``null`` . Setting a ``nextToken`` value that was not returned in your previous results causes an ``InvalidNextTokenException`` to occur. 

  

  

