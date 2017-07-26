[ :ref:`aws <cli:aws>` . :ref:`cloudwatch <cli:aws cloudwatch>` ]

.. _cli:aws cloudwatch list-metrics:


************
list-metrics
************



===========
Description
===========



Returns a list of valid metrics stored for the AWS account owner. Returned metrics can be used with  get-metric-statistics to obtain statistical data for a given metric. 

 

.. note::

  Up to 500 results are returned for any one call. To retrieve further results, use returned ``next-token`` values with subsequent ``list-metrics`` operations. 

 

.. note::

  If you create a metric with the  put-metric-data action, allow up to fifteen minutes for the metric to appear in calls to the ``list-metrics`` action. Statistics about the metric, however, are available sooner using  get-metric-statistics . 



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
  [--generate-cli-skeleton]




=======
Options
=======

``--namespace`` (string)


  The namespace to filter against. 

  

``--metric-name`` (string)


  The name of the metric to filter against. 

  

``--dimensions`` (list)


  A list of dimensions to filter against. 

  



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

   

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``next-token`` will be provided in the output that you can use to resume pagination. This ``next-token`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

  

  A list of metrics used to generate statistics for an AWS account. 

  

  (structure)

    

    The ``Metric`` data type contains information about a specific metric. If you call  list-metrics , Amazon CloudWatch returns information contained by this data type. 

     

    The example in the Examples section publishes two metrics named buffers and latency. Both metrics are in the examples namespace. Both metrics have two dimensions, InstanceID and InstanceType. 

    

    Namespace -> (string)

      

      The namespace of the metric. 

      

      

    MetricName -> (string)

      

      The name of the metric. 

      

      

    Dimensions -> (list)

      

      A list of dimensions associated with the metric. 

      

      (structure)

        

        The ``Dimension`` data type further expands on the identity of a metric using a Name, Value pair. 

         

        For examples that use one or more dimensions, see  put-metric-data .

        

        Name -> (string)

          

          The name of the dimension. 

          

          

        Value -> (string)

          

          The value representing the dimension measurement 

          

          

        

      

    

  

NextToken -> (string)

  

  A string that marks the start of the next batch of returned results. 

  

  

