[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-reserved-instances-offerings:


*************************************
describe-reserved-instances-offerings
*************************************



===========
Description
===========



Describes Reserved Instance offerings that are available for purchase. With Reserved Instances, you purchase the right to launch instances for a period of time. During that time period, you do not receive insufficient capacity errors, and you pay a lower usage rate than the rate charged for On-Demand instances for the actual time used.

 

If you have listed your own Reserved Instances for sale in the Reserved Instance Marketplace, they will be excluded from these results. This is to ensure that you do not purchase your own Reserved Instances.

 

For more information, see `Reserved Instance Marketplace <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ri-market-general.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeReservedInstancesOfferings>`_


``describe-reserved-instances-offerings`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``ReservedInstancesOfferings``


========
Synopsis
========

::

    describe-reserved-instances-offerings
  [--availability-zone <value>]
  [--filters <value>]
  [--include-marketplace | --no-include-marketplace]
  [--instance-type <value>]
  [--max-duration <value>]
  [--max-instance-count <value>]
  [--min-duration <value>]
  [--offering-class <value>]
  [--product-description <value>]
  [--reserved-instances-offering-ids <value>]
  [--dry-run | --no-dry-run]
  [--instance-tenancy <value>]
  [--offering-type <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--availability-zone`` (string)


  The Availability Zone in which the Reserved Instance can be used.

  

``--filters`` (list)


  One or more filters.

   

   
  * ``availability-zone`` - The Availability Zone where the Reserved Instance can be used. 
   
  * ``duration`` - The duration of the Reserved Instance (for example, one year or three years), in seconds (``31536000`` | ``94608000`` ). 
   
  * ``fixed-price`` - The purchase price of the Reserved Instance (for example, 9800.0). 
   
  * ``instance-type`` - The instance type that is covered by the reservation. 
   
  * ``marketplace`` - Set to ``true`` to show only Reserved Instance Marketplace offerings. When this filter is not used, which is the default behavior, all offerings from both AWS and the Reserved Instance Marketplace are listed. 
   
  * ``product-description`` - The Reserved Instance product platform description. Instances that include ``(Amazon VPC)`` in the product platform description will only be displayed to EC2-Classic account holders and are for use with Amazon VPC. (``Linux/UNIX`` | ``Linux/UNIX (Amazon VPC)`` | ``SUSE Linux`` | ``SUSE Linux (Amazon VPC)`` | ``Red Hat Enterprise Linux`` | ``Red Hat Enterprise Linux (Amazon VPC)`` | ``Windows`` | ``Windows (Amazon VPC)`` | ``Windows with SQL Server Standard`` | ``Windows with SQL Server Standard (Amazon VPC)`` | ``Windows with SQL Server Web`` | ``Windows with SQL Server Web (Amazon VPC)`` | ``Windows with SQL Server Enterprise`` | ``Windows with SQL Server Enterprise (Amazon VPC)`` )  
   
  * ``reserved-instances-offering-id`` - The Reserved Instances offering ID. 
   
  * ``scope`` - The scope of the Reserved Instance (``Availability Zone`` or ``Region`` ). 
   
  * ``usage-price`` - The usage price of the Reserved Instance, per hour (for example, 0.84). 
   

  



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



``--include-marketplace`` | ``--no-include-marketplace`` (boolean)


  Include Reserved Instance Marketplace offerings in the response.

  

``--instance-type`` (string)


  The instance type that the reservation will cover (for example, ``m1.small`` ). For more information, see `Instance Types <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-types.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .

  

  Possible values:

  
  *   ``t1.micro``

  
  *   ``t2.nano``

  
  *   ``t2.micro``

  
  *   ``t2.small``

  
  *   ``t2.medium``

  
  *   ``t2.large``

  
  *   ``t2.xlarge``

  
  *   ``t2.2xlarge``

  
  *   ``m1.small``

  
  *   ``m1.medium``

  
  *   ``m1.large``

  
  *   ``m1.xlarge``

  
  *   ``m3.medium``

  
  *   ``m3.large``

  
  *   ``m3.xlarge``

  
  *   ``m3.2xlarge``

  
  *   ``m4.large``

  
  *   ``m4.xlarge``

  
  *   ``m4.2xlarge``

  
  *   ``m4.4xlarge``

  
  *   ``m4.10xlarge``

  
  *   ``m4.16xlarge``

  
  *   ``m2.xlarge``

  
  *   ``m2.2xlarge``

  
  *   ``m2.4xlarge``

  
  *   ``cr1.8xlarge``

  
  *   ``r3.large``

  
  *   ``r3.xlarge``

  
  *   ``r3.2xlarge``

  
  *   ``r3.4xlarge``

  
  *   ``r3.8xlarge``

  
  *   ``r4.large``

  
  *   ``r4.xlarge``

  
  *   ``r4.2xlarge``

  
  *   ``r4.4xlarge``

  
  *   ``r4.8xlarge``

  
  *   ``r4.16xlarge``

  
  *   ``x1.16xlarge``

  
  *   ``x1.32xlarge``

  
  *   ``i2.xlarge``

  
  *   ``i2.2xlarge``

  
  *   ``i2.4xlarge``

  
  *   ``i2.8xlarge``

  
  *   ``i3.large``

  
  *   ``i3.xlarge``

  
  *   ``i3.2xlarge``

  
  *   ``i3.4xlarge``

  
  *   ``i3.8xlarge``

  
  *   ``i3.16xlarge``

  
  *   ``hi1.4xlarge``

  
  *   ``hs1.8xlarge``

  
  *   ``c1.medium``

  
  *   ``c1.xlarge``

  
  *   ``c3.large``

  
  *   ``c3.xlarge``

  
  *   ``c3.2xlarge``

  
  *   ``c3.4xlarge``

  
  *   ``c3.8xlarge``

  
  *   ``c4.large``

  
  *   ``c4.xlarge``

  
  *   ``c4.2xlarge``

  
  *   ``c4.4xlarge``

  
  *   ``c4.8xlarge``

  
  *   ``cc1.4xlarge``

  
  *   ``cc2.8xlarge``

  
  *   ``g2.2xlarge``

  
  *   ``g2.8xlarge``

  
  *   ``g3.4xlarge``

  
  *   ``g3.8xlarge``

  
  *   ``g3.16xlarge``

  
  *   ``cg1.4xlarge``

  
  *   ``p2.xlarge``

  
  *   ``p2.8xlarge``

  
  *   ``p2.16xlarge``

  
  *   ``d2.xlarge``

  
  *   ``d2.2xlarge``

  
  *   ``d2.4xlarge``

  
  *   ``d2.8xlarge``

  
  *   ``f1.2xlarge``

  
  *   ``f1.16xlarge``

  

  

``--max-duration`` (long)


  The maximum duration (in seconds) to filter when searching for offerings.

   

  Default: 94608000 (3 years)

  

``--max-instance-count`` (integer)


  The maximum number of instances to filter when searching for offerings.

   

  Default: 20

  

``--min-duration`` (long)


  The minimum duration (in seconds) to filter when searching for offerings.

   

  Default: 2592000 (1 month)

  

``--offering-class`` (string)


  The offering class of the Reserved Instance. Can be ``standard`` or ``convertible`` .

  

  Possible values:

  
  *   ``standard``

  
  *   ``convertible``

  

  

``--product-description`` (string)


  The Reserved Instance product platform description. Instances that include ``(Amazon VPC)`` in the description are for use with Amazon VPC.

  

  Possible values:

  
  *   ``Linux/UNIX``

  
  *   ``Linux/UNIX (Amazon VPC)``

  
  *   ``Windows``

  
  *   ``Windows (Amazon VPC)``

  

  

``--reserved-instances-offering-ids`` (list)


  One or more Reserved Instances offering IDs.

  



Syntax::

  "string" "string" ...



``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--instance-tenancy`` (string)


  The tenancy of the instances covered by the reservation. A Reserved Instance with a tenancy of ``dedicated`` is applied to instances that run in a VPC on single-tenant hardware (i.e., Dedicated Instances).

   

   **Important:** The ``host`` value cannot be used with this parameter. Use the ``default`` or ``dedicated`` values only.

   

  Default: ``default``  

  

  Possible values:

  
  *   ``default``

  
  *   ``dedicated``

  
  *   ``host``

  

  

``--offering-type`` (string)


  The Reserved Instance offering type. If you are using tools that predate the 2011-11-01 API version, you only have access to the ``Medium Utilization`` Reserved Instance offering type. 

  

  Possible values:

  
  *   ``Heavy Utilization``

  
  *   ``Medium Utilization``

  
  *   ``Light Utilization``

  
  *   ``No Upfront``

  
  *   ``Partial Upfront``

  
  *   ``All Upfront``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe Reserved Instances offerings**

This example command describes all Reserved Instances available for purchase in the region.

Command::

  aws ec2 describe-reserved-instances-offerings

Output::

  {
    "ReservedInstancesOfferings": [
        {
            "OfferingType": "Partial Upfront",
            "AvailabilityZone": "us-east-1b",
            "InstanceTenancy": "default",
            "PricingDetails": [],
            "ProductDescription": "Red Hat Enterprise Linux",
            "UsagePrice": 0.0,
            "RecurringCharges": [
                {
                    "Amount": 0.088,
                    "Frequency": "Hourly"
                }
            ],
            "Marketplace": false,
            "CurrencyCode": "USD",
            "FixedPrice": 631.0,
            "Duration": 94608000,
            "ReservedInstancesOfferingId": "9a06095a-bdc6-47fe-a94a-2a382f016040",
            "InstanceType": "c1.medium"
        },
        {
            "OfferingType": "PartialUpfront",
            "AvailabilityZone": "us-east-1b",
            "InstanceTenancy": "default",
            "PricingDetails": [],
            "ProductDescription": "Linux/UNIX",
            "UsagePrice": 0.0,
            "RecurringCharges": [
                {
                    "Amount": 0.028,
                    "Frequency": "Hourly"
                }
            ],
            "Marketplace": false,
            "CurrencyCode": "USD",
            "FixedPrice": 631.0,
            "Duration": 94608000,
            "ReservedInstancesOfferingId": "bfbefc6c-0d10-418d-b144-7258578d329d",
            "InstanceType": "c1.medium"
        },
    ...
  }

**To describe your Reserved Instances offerings using options**

This example lists Reserved Instances offered by AWS with the following specifications: t1.micro instance types, Windows (Amazon VPC) product, and Heavy Utilization offerings.

Command::

  aws ec2 describe-reserved-instances-offerings --no-include-marketplace --instance-type "t1.micro" --product-description "Windows (Amazon VPC)" --offering-type "no upfront"

Output::

  {
      "ReservedInstancesOfferings": [
        {
            "OfferingType": "No Upfront", 
            "AvailabilityZone": "us-east-1b", 
            "InstanceTenancy": "default", 
            "PricingDetails": [], 
            "ProductDescription": "Windows", 
            "UsagePrice": 0.0, 
            "RecurringCharges": [
                {
                    "Amount": 0.015, 
                    "Frequency": "Hourly"
                }
            ], 
            "Marketplace": false, 
            "CurrencyCode": "USD", 
            "FixedPrice": 0.0, 
            "Duration": 31536000, 
            "ReservedInstancesOfferingId": "c48ab04c-fe69-4f94-8e39-a23842292823", 
            "InstanceType": "t1.micro"
        }, 

		...
        {
            "OfferingType": "No Upfront", 
            "AvailabilityZone": "us-east-1d", 
            "InstanceTenancy": "default", 
            "PricingDetails": [], 
            "ProductDescription": "Windows (Amazon VPC)", 
            "UsagePrice": 0.0, 
            "RecurringCharges": [
                {
                    "Amount": 0.015, 
                    "Frequency": "Hourly"
                }
            ], 
            "Marketplace": false, 
            "CurrencyCode": "USD", 
            "FixedPrice": 0.0, 
            "Duration": 31536000, 
            "ReservedInstancesOfferingId": "3a98bf7d-2123-42d4-b4f5-8dbec4b06dc6", 
            "InstanceType": "t1.micro"
        }
      ]
  }



======
Output
======

ReservedInstancesOfferings -> (list)

  

  A list of Reserved Instances offerings.

  

  (structure)

    

    Describes a Reserved Instance offering.

    

    AvailabilityZone -> (string)

      

      The Availability Zone in which the Reserved Instance can be used.

      

      

    Duration -> (long)

      

      The duration of the Reserved Instance, in seconds.

      

      

    FixedPrice -> (float)

      

      The purchase price of the Reserved Instance.

      

      

    InstanceType -> (string)

      

      The instance type on which the Reserved Instance can be used.

      

      

    ProductDescription -> (string)

      

      The Reserved Instance product platform description.

      

      

    ReservedInstancesOfferingId -> (string)

      

      The ID of the Reserved Instance offering. This is the offering ID used in  get-reserved-instances-exchange-quote to confirm that an exchange can be made.

      

      

    UsagePrice -> (float)

      

      The usage price of the Reserved Instance, per hour.

      

      

    CurrencyCode -> (string)

      

      The currency of the Reserved Instance offering you are purchasing. It's specified using ISO 4217 standard currency codes. At this time, the only supported currency is ``USD`` .

      

      

    InstanceTenancy -> (string)

      

      The tenancy of the instance.

      

      

    Marketplace -> (boolean)

      

      Indicates whether the offering is available through the Reserved Instance Marketplace (resale) or AWS. If it's a Reserved Instance Marketplace offering, this is ``true`` .

      

      

    OfferingClass -> (string)

      

      If ``convertible`` it can be exchanged for Reserved Instances of the same or higher monetary value, with different configurations. If ``standard`` , it is not possible to perform an exchange.

      

      

    OfferingType -> (string)

      

      The Reserved Instance offering type.

      

      

    PricingDetails -> (list)

      

      The pricing details of the Reserved Instance offering.

      

      (structure)

        

        Describes a Reserved Instance offering.

        

        Count -> (integer)

          

          The number of reservations available for the price.

          

          

        Price -> (double)

          

          The price per instance.

          

          

        

      

    RecurringCharges -> (list)

      

      The recurring charge tag assigned to the resource.

      

      (structure)

        

        Describes a recurring charge.

        

        Amount -> (double)

          

          The amount of the recurring charge.

          

          

        Frequency -> (string)

          

          The frequency of the recurring charge.

          

          

        

      

    Scope -> (string)

      

      Whether the Reserved Instance is applied to instances in a region or an Availability Zone.

      

      

    

  

NextToken -> (string)

  

  The token to use to retrieve the next page of results. This value is ``null`` when there are no more results to return.

  

  

