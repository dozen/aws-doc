[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 create-flow-logs:


****************
create-flow-logs
****************



===========
Description
===========



Creates one or more flow logs to capture IP traffic for a specific network interface, subnet, or VPC. Flow logs are delivered to a specified log group in Amazon CloudWatch Logs. If you specify a VPC or subnet in the request, a log stream is created in CloudWatch Logs for each network interface in the subnet or VPC. Log streams can include information about accepted and rejected traffic to a network interface. You can view the data in your log streams using Amazon CloudWatch Logs.

 

In your request, you must also specify an IAM role that has permission to publish logs to CloudWatch Logs.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/CreateFlowLogs>`_


========
Synopsis
========

::

    create-flow-logs
  [--client-token <value>]
  --deliver-logs-permission-arn <value>
  --log-group-name <value>
  --resource-ids <value>
  --resource-type <value>
  --traffic-type <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--client-token`` (string)


  Unique, case-sensitive identifier you provide to ensure the idempotency of the request. For more information, see `How to Ensure Idempotency <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Run_Instance_Idempotency.html>`_ .

  

``--deliver-logs-permission-arn`` (string)


  The ARN for the IAM role that's used to post flow logs to a CloudWatch Logs log group.

  

``--log-group-name`` (string)


  The name of the CloudWatch log group.

  

``--resource-ids`` (list)


  One or more subnet, network interface, or VPC IDs.

   

  Constraints: Maximum of 1000 resources

  



Syntax::

  "string" "string" ...



``--resource-type`` (string)


  The type of resource on which to create the flow log.

  

  Possible values:

  
  *   ``VPC``

  
  *   ``Subnet``

  
  *   ``NetworkInterface``

  

  

``--traffic-type`` (string)


  The type of traffic to log.

  

  Possible values:

  
  *   ``ACCEPT``

  
  *   ``REJECT``

  
  *   ``ALL``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a flow log**

This example creates a flow log that captures all rejected traffic for network interface ``eni-aa22bb33``. The flow logs are delivered to a log group in CloudWatch Logs called ``my-flow-logs`` in account 123456789101, using the IAM role ``publishFlowLogs``.

Command::

  aws ec2 create-flow-logs --resource-type NetworkInterface --resource-ids eni-aa22bb33 --traffic-type REJECT --log-group-name my-flow-logs --deliver-logs-permission-arn arn:aws:iam::123456789101:role/publishFlowLogs

Output::

  {
    "Unsuccessful": [], 
    "FlowLogIds": [
      "fl-1a2b3c4d"
    ], 
    "ClientToken": "lO+mDZGO+HCFEXAMPLEfWNO00bInKkBcLfrC"
  }

======
Output
======

ClientToken -> (string)

  

  Unique, case-sensitive identifier you provide to ensure the idempotency of the request.

  

  

FlowLogIds -> (list)

  

  The IDs of the flow logs.

  

  (string)

    

    

  

Unsuccessful -> (list)

  

  Information about the flow logs that could not be created successfully.

  

  (structure)

    

    Information about items that were not successfully processed in a batch call.

    

    Error -> (structure)

      

      Information about the error.

      

      Code -> (string)

        

        The error code.

        

        

      Message -> (string)

        

        The error message accompanying the error code.

        

        

      

    ResourceId -> (string)

      

      The ID of the resource.

      

      

    

  

