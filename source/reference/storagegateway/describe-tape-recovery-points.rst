[ :ref:`aws <cli:aws>` . :ref:`storagegateway <cli:aws storagegateway>` ]

.. _cli:aws storagegateway describe-tape-recovery-points:


*****************************
describe-tape-recovery-points
*****************************



===========
Description
===========



Returns a list of virtual tape recovery points that are available for the specified gateway-VTL.

 

A recovery point is a point in time view of a virtual tape at which all the data on the virtual tape is consistent. If your gateway crashes, virtual tapes that have recovery points can be recovered to a new gateway.



``describe-tape-recovery-points`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``TapeRecoveryPointInfos``


========
Synopsis
========

::

    describe-tape-recovery-points
  --gateway-arn <value>
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--gateway-arn`` (string)


  The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

GatewayARN -> (string)

  

  The Amazon Resource Name (ARN) of the gateway. Use the  list-gateways operation to return a list of gateways for your account and region.

  

  

TapeRecoveryPointInfos -> (list)

  

  An array of TapeRecoveryPointInfos that are available for the specified gateway.

  

  (structure)

    

    Describes a recovery point. 

    

    TapeARN -> (string)

      

      The Amazon Resource Name (ARN) of the virtual tape.

      

      

    TapeRecoveryPointTime -> (timestamp)

      

      The time when the point-in-time view of the virtual tape was replicated for later recovery. 

       

      The string format of the tape recovery point time is in the ISO8601 extended YYYY-MM-DD'T'HH:MM:SS'Z' format.

      

      

    TapeSizeInBytes -> (long)

      

      The size, in bytes, of the virtual tapes to recover.

      

      

    TapeStatus -> (string)

      

      

    

  

Marker -> (string)

  

  An opaque string that indicates the position at which the virtual tape recovery points that were listed for description ended.

   

  Use this marker in your next request to list the next set of virtual tape recovery points in the list. If there are no more recovery points to describe, this field does not appear in the response.

  

  

