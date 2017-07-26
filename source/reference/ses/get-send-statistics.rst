[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses get-send-statistics:


*******************
get-send-statistics
*******************



===========
Description
===========



Returns the user's sending statistics. The result is a list of data points, representing the last two weeks of sending activity. 

 

Each data point in the list contains statistics for a 15-minute interval.

 

This action is throttled at one request per second.



========
Synopsis
========

::

    get-send-statistics
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To get your Amazon SES sending statistics**

The following example uses the ``get-send-statistics`` command to return your Amazon SES sending statistics ::

    aws ses get-send-statistics

Output::

 {
    "SendDataPoints": [
        {
            "Complaints": 0,
            "Timestamp": "2013-06-12T19:32:00Z",
            "DeliveryAttempts": 2,
            "Bounces": 0,
            "Rejects": 0
        },
        {
            "Complaints": 0,
            "Timestamp": "2013-06-12T00:47:00Z",
            "DeliveryAttempts": 1,
            "Bounces": 0,
            "Rejects": 0
        }
    ]
 }


The result is a list of data points, representing the last two weeks of sending activity. Each data point in the list
contains statistics for a 15-minute interval.

In this example, there are only two data points because the only emails that the user sent in the last two weeks fell
within two 15-minute intervals.


For more information, see `Monitoring Your Amazon SES Usage Statistics`_ in the *Amazon Simple Email Service Developer Guide*.

.. _`Monitoring Your Amazon SES Usage Statistics`: http://docs.aws.amazon.com/ses/latest/DeveloperGuide/monitor-usage-statistics.html


======
Output
======

SendDataPoints -> (list)

  

  A list of data points, each of which represents 15 minutes of activity.

  

  (structure)

    

    Represents sending statistics data. Each ``SendDataPoint`` contains statistics for a 15-minute period of sending activity. 

    

    Timestamp -> (timestamp)

      

      Time of the data point.

      

      

    DeliveryAttempts -> (long)

      

      Number of emails that have been enqueued for sending.

      

      

    Bounces -> (long)

      

      Number of emails that have bounced.

      

      

    Complaints -> (long)

      

      Number of unwanted emails that were rejected by recipients.

      

      

    Rejects -> (long)

      

      Number of emails rejected by Amazon SES.

      

      

    

  

