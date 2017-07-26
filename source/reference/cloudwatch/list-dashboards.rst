[ :ref:`aws <cli:aws>` . :ref:`cloudwatch <cli:aws cloudwatch>` ]

.. _cli:aws cloudwatch list-dashboards:


***************
list-dashboards
***************



===========
Description
===========



Returns a list of the dashboards for your account. If you include ``dashboard-name-prefix`` , only those dashboards with names starting with the prefix are listed. Otherwise, all dashboards in your account are listed. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/monitoring-2010-08-01/ListDashboards>`_


========
Synopsis
========

::

    list-dashboards
  [--dashboard-name-prefix <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dashboard-name-prefix`` (string)


  If you specify this parameter, only the dashboards with names starting with the specified string are listed. The maximum length is 255, and valid characters are A-Z, a-z, 0-9, ".", "-", and "_". 

  

``--next-token`` (string)


  The token returned by a previous call to indicate that there is more data available.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DashboardEntries -> (list)

  

  The list of matching dashboards.

  

  (structure)

    

    Represents a specific dashboard.

    

    DashboardName -> (string)

      

      The name of the dashboard.

      

      

    DashboardArn -> (string)

      

      The Amazon Resource Name (ARN) of the dashboard.

      

      

    LastModified -> (timestamp)

      

      The time stamp of when the dashboard was last modified, either by an API call or through the console. This number is expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC.

      

      

    Size -> (long)

      

      The size of the dashboard, in bytes.

      

      

    

  

NextToken -> (string)

  

  The token that marks the start of the next batch of returned results.

  

  

