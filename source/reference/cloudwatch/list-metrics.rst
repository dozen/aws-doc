[ :ref:`aws <cli:aws>` . :ref:`cloudwatch <cli:aws cloudwatch>` ]

.. _cli:aws cloudwatch list-metrics:


************
list-metrics
************



===========
Description
===========



List the specified metrics. You can use the returned metrics with  get-metric-statistics to obtain statistical data.

 

Up to 500 results are returned for any one call. To retrieve additional results, use the returned token with subsequent calls.

 

After you create a metric, allow up to fifteen minutes before the metric appears. Statistics about the metric, however, are available sooner using  get-metric-statistics .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/monitoring-2010-08-01/ListMetrics>`_


``list-metrics`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Metrics``


========
Synopsis
========

::

    list-metrics
  [--namespace <value>]
  [--metric-name <value>]
  [--dimensions <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--namespace`` (string)


  The namespace to filter against.

  

``--metric-name`` (string)


  The name of the metric to filter against.

  

``--dimensions`` (list)


  The dimensions to filter against.

  



Shorthand Syntax::

    Name=string,Value=string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Value": "string"
    }
    ...
  ]



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``next-token`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``next-token`` is provided in the command's output. To resume pagination, provide the ``next-token`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``next-token`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To list the metrics for Amazon EC2**

The following example uses the ``list-metrics`` command to list the metrics for Amazon SNS.::

  aws cloudwatch list-metrics --namespace "AWS/SNS"

Output::

  {
      "Metrics": [
          {
              "Namespace": "AWS/SNS",
              "Dimensions": [
                  {
                      "Name": "TopicName",
                      "Value": "NotifyMe"
                  }
              ],
              "MetricName": "PublishSize"
          },
          {
              "Namespace": "AWS/SNS",
              "Dimensions": [
                  {
                      "Name": "TopicName",
                      "Value": "CFO"
                  }
              ],
              "MetricName": "PublishSize"
          },
          {
              "Namespace": "AWS/SNS",
              "Dimensions": [
                  {
                      "Name": "TopicName",
                      "Value": "NotifyMe"
                  }
              ],
              "MetricName": "NumberOfNotificationsFailed"
          },
          {
              "Namespace": "AWS/SNS",
              "Dimensions": [
                  {
                      "Name": "TopicName",
                      "Value": "NotifyMe"
                  }
              ],
              "MetricName": "NumberOfNotificationsDelivered"
          },
          {
              "Namespace": "AWS/SNS",
              "Dimensions": [
                  {
                      "Name": "TopicName",
                      "Value": "NotifyMe"
                  }
              ],
              "MetricName": "NumberOfMessagesPublished"
          },
          {
              "Namespace": "AWS/SNS",
              "Dimensions": [
                  {
                      "Name": "TopicName",
                      "Value": "CFO"
                  }
              ],
              "MetricName": "NumberOfMessagesPublished"
          },
          {
              "Namespace": "AWS/SNS",
              "Dimensions": [
                  {
                      "Name": "TopicName",
                      "Value": "CFO"
                  }
              ],
              "MetricName": "NumberOfNotificationsDelivered"
          },
          {
              "Namespace": "AWS/SNS",
              "Dimensions": [
                  {
                      "Name": "TopicName",
                      "Value": "CFO"
                  }
              ],
              "MetricName": "NumberOfNotificationsFailed"
          }
      ]
  }



======
Output
======

Metrics -> (list)

  

  The metrics.

  

  (structure)

    

    Represents a specific metric.

    

    Namespace -> (string)

      

      The namespace of the metric.

      

      

    MetricName -> (string)

      

      The name of the metric.

      

      

    Dimensions -> (list)

      

      The dimensions for the metric.

      

      (structure)

        

        Expands the identity of a metric.

        

        Name -> (string)

          

          The name of the dimension.

          

          

        Value -> (string)

          

          The value representing the dimension measurement.

          

          

        

      

    

  

NextToken -> (string)

  

  The token that marks the start of the next batch of returned results.

  

  

