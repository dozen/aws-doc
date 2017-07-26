[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift describe-reserved-nodes:


***********************
describe-reserved-nodes
***********************



===========
Description
===========



Returns the descriptions of the reserved nodes. 



``describe-reserved-nodes`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``ReservedNodes``


========
Synopsis
========

::

    describe-reserved-nodes
  [--reserved-node-id <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--reserved-node-id`` (string)


  Identifier for the node reservation.

  

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



========
Examples
========

Describe Reserved Nodes
-----------------------

This example shows a reserved node offering that has been purchased.

Command::

   aws redshift describe-reserved-nodes

Result::

    {
       "ResponseMetadata": {
          "RequestId": "bc29ce2e-7600-11e2-9949-4b361e7420b7"
       },
       "ReservedNodes": [
          {
             "OfferingType": "Heavy Utilization",
             "FixedPrice": "",
             "NodeType": "dw.hs1.xlarge",
             "ReservedNodeId": "1ba8e2e3-bc01-4d65-b35d-a4a3e931547e",
             "UsagePrice": "",
             "RecurringCharges": [
                {
                   "RecurringChargeAmount": "",
                   "RecurringChargeFrequency": "Hourly"
                } ],
             "NodeCount": 1,
             "State": "payment-pending",
             "StartTime": "2013-02-13T17:08:39.051Z",
             "Duration": 31536000,
             "ReservedNodeOfferingId": "ceb6a579-cf4c-4343-be8b-d832c45ab51c"
          }
       ]
    }



======
Output
======

Marker -> (string)

  

  A value that indicates the starting point for the next set of response records in a subsequent request. If a value is returned in a response, you can retrieve the next set of records by providing this returned marker value in the ``Marker`` parameter and retrying the command. If the ``Marker`` field is empty, all response records have been retrieved for the request. 

  

  

ReservedNodes -> (list)

  

  The list of reserved nodes.

  

  (structure)

    

    Describes a reserved node. You can call the  describe-reserved-node-offerings API to obtain the available reserved node offerings. 

    

    ReservedNodeId -> (string)

      

      The unique identifier for the reservation. 

      

      

    ReservedNodeOfferingId -> (string)

      

      The identifier for the reserved node offering. 

      

      

    NodeType -> (string)

      

      The node type of the reserved node. 

      

      

    StartTime -> (timestamp)

      

      The time the reservation started. You purchase a reserved node offering for a duration. This is the start time of that duration. 

      

      

    Duration -> (integer)

      

      The duration of the node reservation in seconds. 

      

      

    FixedPrice -> (double)

      

      The fixed cost Amazon Redshift charges you for this reserved node. 

      

      

    UsagePrice -> (double)

      

      The hourly rate Amazon Redshift charges you for this reserved node. 

      

      

    CurrencyCode -> (string)

      

      The currency code for the reserved cluster.

      

      

    NodeCount -> (integer)

      

      The number of reserved compute nodes. 

      

      

    State -> (string)

      

      The state of the reserved compute node. 

       

      Possible Values:

       

       
      * pending-payment-This reserved node has recently been purchased, and the sale has been approved, but payment has not yet been confirmed.
       
      * active-This reserved node is owned by the caller and is available for use.
       
      * payment-failed-Payment failed for the purchase attempt.
       

      

      

    OfferingType -> (string)

      

      The anticipated utilization of the reserved node, as defined in the reserved node offering.

      

      

    RecurringCharges -> (list)

      

      The recurring charges for the reserved node.

      

      (structure)

        

        Describes a recurring charge.

        

        RecurringChargeAmount -> (double)

          

          The amount charged per the period of time specified by the recurring charge frequency. 

          

          

        RecurringChargeFrequency -> (string)

          

          The frequency at which the recurring charge amount is applied.

          

          

        

      

    

  

