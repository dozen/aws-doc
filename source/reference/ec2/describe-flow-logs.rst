[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-flow-logs:


******************
describe-flow-logs
******************



===========
Description
===========



Describes one or more flow logs. To view the information in your flow logs (the log streams for the network interfaces), you must use the CloudWatch Logs console or the CloudWatch Logs API.



========
Synopsis
========

::

    describe-flow-logs
  [--flow-log-ids <value>]
  [--filter <value>]
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--flow-log-ids`` (list)


  One or more flow log IDs.

  



Syntax::

  "string" "string" ...



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



``--next-token`` (string)


  The token to retrieve the next page of results.

  

``--max-results`` (integer)


  The maximum number of results to return for the request in a single page. The remaining results can be seen by sending another request with the returned ``NextToken`` value. This value can be between 5 and 1000; if ``MaxResults`` is given a value larger than 1000, only 1000 results are returned. You cannot specify this parameter and the flow log IDs parameter in the same request.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

      

      

    FlowLogId -> (string)

      

      The flow log ID.

      

      

    FlowLogStatus -> (string)

      

      The status of the flow log (``ACTIVE`` ).

      

      

    ResourceId -> (string)

      

      The ID of the resource on which the flow log was created.

      

      

    TrafficType -> (string)

      

      The type of traffic captured for the flow log.

      

      

    LogGroupName -> (string)

      

      The name of the flow log group.

      

      

    DeliverLogsStatus -> (string)

      

      The status of the logs delivery (``SUCCESS`` | ``FAILED`` ).

      

      

    DeliverLogsErrorMessage -> (string)

      

      Information about the error that occurred. ``Rate limited`` indicates that CloudWatch logs throttling has been applied for one or more network interfaces, or that you've reached the limit on the number of CloudWatch Logs log groups that you can create. ``Access error`` indicates that the IAM role associated with the flow log does not have sufficient permissions to publish to CloudWatch Logs. ``Unknown error`` indicates an internal error.

      

      

    DeliverLogsPermissionArn -> (string)

      

      The ARN of the IAM role that posts logs to CloudWatch Logs.

      

      

    

  

NextToken -> (string)

  

  The token to use to retrieve the next page of results. This value is ``null`` when there are no more results to return.

  

  

