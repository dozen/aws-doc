[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift describe-resize:


***************
describe-resize
***************



===========
Description
===========



Returns information about the last resize operation for the specified cluster. If no resize operation has ever been initiated for the specified cluster, a ``HTTP 404`` error is returned. If a resize operation was initiated and completed, the status of the resize remains as ``SUCCEEDED`` until the next resize. 

 

A resize operation can be requested using  modify-cluster and specifying a different number or type of nodes for the cluster. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/redshift-2012-12-01/DescribeResize>`_


========
Synopsis
========

::

    describe-resize
  --cluster-identifier <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cluster-identifier`` (string)


  The unique identifier of a cluster whose resize progress you are requesting. This parameter is case-sensitive.

   

  By default, resize operations for all clusters defined for an AWS account are returned.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

Describe Resize
---------------

This example describes the latest resize of a cluster. The request was for 3 nodes of type ``dw.hs1.8xlarge``.

Command::

   aws redshift describe-resize --cluster-identifier mycluster

Result::

    {
       "Status": "NONE",
       "TargetClusterType": "multi-node",
       "TargetNodeType": "dw.hs1.8xlarge",
       "ResponseMetadata": {
          "RequestId": "9f52b0b4-7733-11e2-aa9b-318b2909bd27"
       },
       "TargetNumberOfNodes": "3"
    }



======
Output
======

TargetNodeType -> (string)

  

  The node type that the cluster will have after the resize operation is complete.

  

  

TargetNumberOfNodes -> (integer)

  

  The number of nodes that the cluster will have after the resize operation is complete.

  

  

TargetClusterType -> (string)

  

  The cluster type after the resize operation is complete.

   

  Valid Values: ``multi-node`` | ``single-node``  

  

  

Status -> (string)

  

  The status of the resize operation.

   

  Valid Values: ``NONE`` | ``IN_PROGRESS`` | ``FAILED`` | ``SUCCEEDED``  

  

  

ImportTablesCompleted -> (list)

  

  The names of tables that have been completely imported .

   

  Valid Values: List of table names.

  

  (string)

    

    

  

ImportTablesInProgress -> (list)

  

  The names of tables that are being currently imported.

   

  Valid Values: List of table names.

  

  (string)

    

    

  

ImportTablesNotStarted -> (list)

  

  The names of tables that have not been yet imported.

   

  Valid Values: List of table names

  

  (string)

    

    

  

AvgResizeRateInMegaBytesPerSecond -> (double)

  

  The average rate of the resize operation over the last few minutes, measured in megabytes per second. After the resize operation completes, this value shows the average rate of the entire resize operation.

  

  

TotalResizeDataInMegaBytes -> (long)

  

  The estimated total amount of data, in megabytes, on the cluster before the resize operation began.

  

  

ProgressInMegaBytes -> (long)

  

  While the resize operation is in progress, this value shows the current amount of data, in megabytes, that has been processed so far. When the resize operation is complete, this value shows the total amount of data, in megabytes, on the cluster, which may be more or less than TotalResizeDataInMegaBytes (the estimated total amount of data before resize).

  

  

ElapsedTimeInSeconds -> (long)

  

  The amount of seconds that have elapsed since the resize operation began. After the resize operation completes, this value shows the total actual time, in seconds, for the resize operation.

  

  

EstimatedTimeToCompletionInSeconds -> (long)

  

  The estimated time remaining, in seconds, until the resize operation is complete. This value is calculated based on the average resize rate and the estimated amount of data remaining to be processed. Once the resize operation is complete, this value will be 0.

  

  

