[ :ref:`aws <cli:aws>` . :ref:`logs <cli:aws logs>` ]

.. _cli:aws logs put-destination:


***************
put-destination
***************



===========
Description
===========



Creates or updates a ``Destination`` . A destination encapsulates a physical resource (such as a Kinesis stream) and allows you to subscribe to a real-time stream of log events of a different account, ingested through ``put-log-events`` requests. Currently, the only supported physical resource is a Amazon Kinesis stream belonging to the same account as the destination. 

 

A destination controls what is written to its Amazon Kinesis stream through an access policy. By default, put-destination does not set any access policy with the destination, which means a cross-account user will not be able to call ``put-subscription-filter`` against this destination. To enable that, the destination owner must call ``put-destination-policy`` after PutDestination. 



========
Synopsis
========

::

    put-destination
  --destination-name <value>
  --target-arn <value>
  --role-arn <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--destination-name`` (string)


  A name for the destination.

  

``--target-arn`` (string)


  The ARN of an Amazon Kinesis stream to deliver matching log events to.

  

``--role-arn`` (string)


  The ARN of an IAM role that grants CloudWatch Logs permissions to do Amazon Kinesis PutRecord requests on the desitnation stream.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

destination -> (structure)

  

  A cross account destination that is the recipient of subscription log events.

  

  destinationName -> (string)

    

    Name of the destination.

    

    

  targetArn -> (string)

    

    ARN of the physical target where the log events will be delivered (eg. ARN of a Kinesis stream).

    

    

  roleArn -> (string)

    

    A role for impersonation for delivering log events to the target.

    

    

  accessPolicy -> (string)

    

    An IAM policy document that governs which AWS accounts can create subscription filters against this destination.

    

    

  arn -> (string)

    

    ARN of this destination.

    

    

  creationTime -> (long)

    

    A point in time expressed as the number of milliseconds since Jan 1, 1970 00:00:00 UTC specifying when this destination was created.

    

    

  

