[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift describe-reserved-node-offerings:


********************************
describe-reserved-node-offerings
********************************



===========
Description
===========



Returns a list of the available reserved node offerings by Amazon Redshift with their descriptions including the node type, the fixed and recurring costs of reserving the node and duration the node will be reserved for you. These descriptions help you determine which reserve node offering you want to purchase. You then use the unique offering ID in you call to  purchase-reserved-node-offering to reserve one or more nodes for your Amazon Redshift cluster. 

 

For more information about reserved node offerings, go to `Purchasing Reserved Nodes`_ in the *Amazon Redshift Cluster Management Guide* . 



``describe-reserved-node-offerings`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``ReservedNodeOfferings``


========
Synopsis
========

::

    describe-reserved-node-offerings
  [--reserved-node-offering-id <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--reserved-node-offering-id`` (string)


  The unique identifier for the offering.

  

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

Describe Reserved Node Offerings
--------------------------------

This example shows all of the reserved node offerings that are available for
purchase.

Command::

   aws redshift describe-reserved-node-offerings

Result::

    {
       "ReservedNodeOfferings": [
          {
             "OfferingType": "Heavy Utilization",
             "FixedPrice": "",
             "NodeType": "dw.hs1.xlarge",
             "UsagePrice": "",
             "RecurringCharges": [
                {
                   "RecurringChargeAmount": "",
                   "RecurringChargeFrequency": "Hourly"
                } ],
             "Duration": 31536000,
             "ReservedNodeOfferingId": "ceb6a579-cf4c-4343-be8b-d832c45ab51c"
          },
          {
             "OfferingType": "Heavy Utilization",
             "FixedPrice": "",
             "NodeType": "dw.hs1.8xlarge",
             "UsagePrice": "",
             "RecurringCharges": [
                {
                "RecurringChargeAmount": "",
                "RecurringChargeFrequency": "Hourly"
                } ],
             "Duration": 31536000,
             "ReservedNodeOfferingId": "e5a2ff3b-352d-4a9c-ad7d-373c4cab5dd2"
          },
          ...remaining output omitted...
       ],
       "ResponseMetadata": {
          "RequestId": "8b1a1a43-75ff-11e2-9666-e142fe91ddd1"
       }
    }

If you want to purchase a reserved node offering, you can call ``purchase-reserved-node-offering`` using a valid
*ReservedNodeOfferingId*.



======
Output
======

Marker -> (string)

  

  A value that indicates the starting point for the next set of response records in a subsequent request. If a value is returned in a response, you can retrieve the next set of records by providing this returned marker value in the ``Marker`` parameter and retrying the command. If the ``Marker`` field is empty, all response records have been retrieved for the request. 

  

  

ReservedNodeOfferings -> (list)

  

  A list of reserved node offerings.

  

  (structure)

    

    Describes a reserved node offering.

    

    ReservedNodeOfferingId -> (string)

      

      The offering identifier. 

      

      

    NodeType -> (string)

      

      The node type offered by the reserved node offering. 

      

      

    Duration -> (integer)

      

      The duration, in seconds, for which the offering will reserve the node. 

      

      

    FixedPrice -> (double)

      

      The upfront fixed charge you will pay to purchase the specific reserved node offering. 

      

      

    UsagePrice -> (double)

      

      The rate you are charged for each hour the cluster that is using the offering is running. 

      

      

    CurrencyCode -> (string)

      

      The currency code for the compute nodes offering. 

      

      

    OfferingType -> (string)

      

      The anticipated utilization of the reserved node, as defined in the reserved node offering.

      

      

    RecurringCharges -> (list)

      

      The charge to your account regardless of whether you are creating any clusters using the node offering. Recurring charges are only in effect for heavy-utilization reserved nodes. 

      

      (structure)

        

        Describes a recurring charge.

        

        RecurringChargeAmount -> (double)

          

          The amount charged per the period of time specified by the recurring charge frequency. 

          

          

        RecurringChargeFrequency -> (string)

          

          The frequency at which the recurring charge amount is applied.

          

          

        

      

    

  



.. _Purchasing Reserved Nodes: http://docs.aws.amazon.com/redshift/latest/mgmt/purchase-reserved-node-instance.html
