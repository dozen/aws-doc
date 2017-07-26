[ :ref:`aws <cli:aws>` . :ref:`cloudwatch <cli:aws cloudwatch>` ]

.. _cli:aws cloudwatch describe-alarm-history:


**********************
describe-alarm-history
**********************



===========
Description
===========



Retrieves history for the specified alarm. Filter alarms by date range or item type. If an alarm name is not specified, Amazon CloudWatch returns histories for all of the owner's alarms. 

 

.. note::

  Amazon CloudWatch retains the history of an alarm for two weeks, whether or not you delete the alarm. 



``describe-alarm-history`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``AlarmHistoryItems``


========
Synopsis
========

::

    describe-alarm-history
  [--alarm-name <value>]
  [--history-item-type <value>]
  [--start-date <value>]
  [--end-date <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--alarm-name`` (string)


  The name of the alarm. 

  

``--history-item-type`` (string)


  The type of alarm histories to retrieve. 

  

  Possible values:

  
  *   ``ConfigurationUpdate``

  
  *   ``StateUpdate``

  
  *   ``Action``

  

  

``--start-date`` (timestamp)


  The starting date to retrieve alarm history. 

  

``--end-date`` (timestamp)


  The ending date to retrieve alarm history. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``next-token`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``next-token`` will be provided in the output that you can use to resume pagination. This ``next-token`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To retrieve history for an alarm**

The following example uses the ``describe-alarm-history`` command to retrieve history for the Amazon
CloudWatch alarm named "myalarm"::

  aws cloudwatch describe-alarm-history --alarm-name "myalarm" --history-item-type StateUpdate

Output::

  {
      "AlarmHistoryItems": [
          {
              "Timestamp": "2014-04-09T18:59:06.442Z",
              "HistoryItemType": "StateUpdate",
              "AlarmName": "myalarm",
              "HistoryData": "{\"version\":\"1.0\",\"oldState\":{\"stateValue\":\"ALARM\",\"stateReason\":\"testing purposes\"},\"newState\":{\"stateValue\":\"OK\",\"stateReason\":\"Threshold Crossed: 2 datapoints were not greater than the threshold (70.0). The most recent datapoints: [38.958, 40.292].\",\"stateReasonData\":{\"version\":\"1.0\",\"queryDate\":\"2014-04-09T18:59:06.419+0000\",\"startDate\":\"2014-04-09T18:44:00.000+0000\",\"statistic\":\"Average\",\"period\":300,\"recentDatapoints\":[38.958,40.292],\"threshold\":70.0}}}",
              "HistorySummary": "Alarm updated from ALARM to OK"
          },
          {
              "Timestamp": "2014-04-09T18:59:05.805Z",
              "HistoryItemType": "StateUpdate",
              "AlarmName": "myalarm",
              "HistoryData": "{\"version\":\"1.0\",\"oldState\":{\"stateValue\":\"OK\",\"stateReason\":\"Threshold Crossed: 2 datapoints were not greater than the threshold (70.0). The most recent datapoints: [38.839999999999996, 39.714].\",\"stateReasonData\":{\"version\":\"1.0\",\"queryDate\":\"2014-03-11T22:45:41.569+0000\",\"startDate\":\"2014-03-11T22:30:00.000+0000\",\"statistic\":\"Average\",\"period\":300,\"recentDatapoints\":[38.839999999999996,39.714],\"threshold\":70.0}},\"newState\":{\"stateValue\":\"ALARM\",\"stateReason\":\"testing purposes\"}}",
              "HistorySummary": "Alarm updated from OK to ALARM"
          }
      ]
  }



======
Output
======

AlarmHistoryItems -> (list)

  

  A list of alarm histories in JSON format. 

  

  (structure)

    

    The ``AlarmHistoryItem`` data type contains descriptive information about the history of a specific alarm. If you call  describe-alarm-history , Amazon CloudWatch returns this data type as part of the DescribeAlarmHistoryResult data type. 

    

    AlarmName -> (string)

      

      The descriptive name for the alarm. 

      

      

    Timestamp -> (timestamp)

      

      The time stamp for the alarm history item. 

      

      

    HistoryItemType -> (string)

      

      The type of alarm history item. 

      

      

    HistorySummary -> (string)

      

      A human-readable summary of the alarm history. 

      

      

    HistoryData -> (string)

      

      Machine-readable data about the alarm in JSON format. 

      

      

    

  

NextToken -> (string)

  

  A string that marks the start of the next batch of returned results. 

  

  

