[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift purchase-reserved-node-offering:


*******************************
purchase-reserved-node-offering
*******************************



===========
Description
===========



Allows you to purchase reserved nodes. Amazon Redshift offers a predefined set of reserved node offerings. You can purchase one or more of the offerings. You can call the  describe-reserved-node-offerings API to obtain the available reserved node offerings. You can call this API by providing a specific reserved node offering and the number of nodes you want to reserve. 

 

For more information about reserved node offerings, go to `Purchasing Reserved Nodes`_ in the *Amazon Redshift Cluster Management Guide* . 



========
Synopsis
========

::

    purchase-reserved-node-offering
  --reserved-node-offering-id <value>
  [--node-count <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--reserved-node-offering-id`` (string)


  The unique identifier of the reserved node offering you want to purchase.

  

``--node-count`` (integer)


  The number of reserved nodes you want to purchase.

   

  Default: ``1`` 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

Purchase a Reserved Node
------------------------

This example shows how to purchase a reserved node offering. The ``reserved-node-offering-id`` is obtained by
calling ``describe-reserved-node-offerings``.

Command::

   aws redshift purchase-reserved-node-offering --reserved-node-offering-id ceb6a579-cf4c-4343-be8b-d832c45ab51c

Result::

    {
       "ReservedNode": {
          "OfferingType": "Heavy Utilization",
          "FixedPrice": "",
          "NodeType": "dw.hs1.xlarge",
          "ReservedNodeId": "1ba8e2e3-bc01-4d65-b35d-a4a3e931547e",
          "UsagePrice": "",
          "RecurringCharges": [
             {
                "RecurringChargeAmount": "",
                "RecurringChargeFrequency": "Hourly"
             }
          ],
          "NodeCount": 1,
          "State": "payment-pending",
          "StartTime": "2013-02-13T17:08:39.051Z",
          "Duration": 31536000,
          "ReservedNodeOfferingId": "ceb6a579-cf4c-4343-be8b-d832c45ab51c"
       },
       "ResponseMetadata": {
          "RequestId": "01bda7bf-7600-11e2-b605-2568d7396e7f"
       }
    }



======
Output
======

ReservedNode -> (structure)

  

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

        

        

      

    

  



.. _Purchasing Reserved Nodes: http://docs.aws.amazon.com/redshift/latest/mgmt/purchase-reserved-node-instance.html
