[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-flow-logs:


******************
describe-flow-logs
******************



===========
Description
===========



Describes one or more flow logs. To view the information in your flow logs (the log streams for the network interfaces), you must use the CloudWatch Logs console or the CloudWatch Logs API.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeFlowLogs>`_


========
Synopsis
========

::

    describe-flow-logs
  [--filter <value>]
  [--flow-log-ids <value>]
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filter`` (list)


  One or more filters.

   

   
  * ``deliver-log-status`` - The status of the logs delivery (``SUCCESS`` | ``FAILED`` ). 
   
  * ``flow-log-id`` - The ID of the flow log. 
   
  * ``log-group-name`` - The name of the log group. 
   
  * ``resource-id`` - The ID of the VPC, subnet, or network interface. 
   
  * ``traffic-type`` - The type of traffic (``ACCEPT`` | ``REJECT`` | ``ALL`` ) 
   

  



Shorthand Syntax::

    Name=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Values": ["string", ...]
    }
    ...
  ]



``--flow-log-ids`` (list)


  One or more flow log IDs.

  



Syntax::

  "string" "string" ...



``--max-results`` (integer)


  The maximum number of results to return for the request in a single page. The remaining results can be seen by sending another request with the returned ``NextToken`` value. This value can be between 5 and 1000; if ``MaxResults`` is given a value larger than 1000, only 1000 results are returned. You cannot specify this parameter and the flow log IDs parameter in the same request.

  

``--next-token`` (string)


  The token to retrieve the next page of results.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe flow logs**

This example describes all of your flow logs.

Command::

  aws ec2 describe-flow-logs

Output::

  {
    "FlowLogs": [
      {
        "ResourceId": "eni-11aa22bb", 
        "CreationTime": "2015-06-12T14:41:15Z", 
        "LogGroupName": "MyFlowLogs", 
        "TrafficType": "ALL", 
        "FlowLogStatus": "ACTIVE", 
        "FlowLogId": "fl-1a2b3c4d", 
        "DeliverLogsPermissionArn": "arn:aws:iam::123456789101:role/flow-logs-role"
      }
    ]
  }
  
This example uses a filter to describe only flow logs that are in the log group ``MyFlowLogs`` in Amazon CloudWatch Logs.
 
Command::
 
  aws ec2 describe-flow-logs --filter "Name=log-group-name,Values=MyFlowLogs"

======
Output
======

FlowLogs -> (list)

  

  Information about the flow logs.

  

  (structure)

    

    Describes a flow log.

    

    CreationTime -> (timestamp)

      

      The date and time the flow log was created.

      

      

    DeliverLogsErrorMessage -> (string)

      

      Information about the error that occurred. ``Rate limited`` indicates that CloudWatch logs throttling has been applied for one or more network interfaces, or that you've reached the limit on the number of CloudWatch Logs log groups that you can create. ``Access error`` indicates that the IAM role associated with the flow log does not have sufficient permissions to publish to CloudWatch Logs. ``Unknown error`` indicates an internal error.

      

      

    DeliverLogsPermissionArn -> (string)

      

      The ARN of the IAM role that posts logs to CloudWatch Logs.

      

      

    DeliverLogsStatus -> (string)

      

      The status of the logs delivery (``SUCCESS`` | ``FAILED`` ).

      

      

    FlowLogId -> (string)

      

      The flow log ID.

      

      

    FlowLogStatus -> (string)

      

      The status of the flow log (``ACTIVE`` ).

      

      

    LogGroupName -> (string)

      

      The name of the flow log group.

      

      

    ResourceId -> (string)

      

      The ID of the resource on which the flow log was created.

      

      

    TrafficType -> (string)

      

      The type of traffic captured for the flow log.

      

      

    

  

NextToken -> (string)

  

  The token to use to retrieve the next page of results. This value is ``null`` when there are no more results to return.

  

  

