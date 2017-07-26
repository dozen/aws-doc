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

 

For more information, see `Reserved Instance Marketplace`_ in the *Amazon Elastic Compute Cloud User Guide* .



``describe-reserved-instances-offerings`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``ReservedInstancesOfferings``


========
Synopsis
========

::

    describe-reserved-instances-offerings
  [--dry-run | --no-dry-run]
  [--reserved-instances-offering-ids <value>]
  [--instance-type <value>]
  [--availability-zone <value>]
  [--product-description <value>]
  [--filters <value>]
  [--instance-tenancy <value>]
  [--offering-type <value>]
  [--include-marketplace | --no-include-marketplace]
  [--min-duration <value>]
  [--max-duration <value>]
  [--max-instance-count <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--reserved-instances-offering-ids`` (list)


  One or more Reserved Instances offering IDs.

  



Syntax::

  "string" "string" ...



``--instance-type`` (string)


  The instance type that the reservation will cover (for example, ``m1.small`` ). For more information, see `Instance Types`_ in the *Amazon Elastic Compute Cloud User Guide* .

  

  Possible values:

  
  *   ``t1.micro``

  
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

  
  *   ``t2.nano``

  
  *   ``t2.micro``

  
  *   ``t2.small``

  
  *   ``t2.medium``

  
  *   ``t2.large``

  
  *   ``m2.xlarge``

  
  *   ``m2.2xlarge``

  
  *   ``m2.4xlarge``

  
  *   ``cr1.8xlarge``

  
  *   ``i2.xlarge``

  
  *   ``i2.2xlarge``

  
  *   ``i2.4xlarge``

  
  *   ``i2.8xlarge``

  
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

  
  *   ``cg1.4xlarge``

  
  *   ``r3.large``

  
  *   ``r3.xlarge``

  
  *   ``r3.2xlarge``

  
  *   ``r3.4xlarge``

  
  *   ``r3.8xlarge``

  
  *   ``d2.xlarge``

  
  *   ``d2.2xlarge``

  
  *   ``d2.4xlarge``

  
  *   ``d2.8xlarge``

  

  

``--availability-zone`` (string)


  The Availability Zone in which the Reserved Instance can be used.

  

``--product-description`` (string)


  The Reserved Instance product platform description. Instances that include ``(Amazon VPC)`` in the description are for use with Amazon VPC.

  

  Possible values:

  
  *   ``Linux/UNIX``

  
  *   ``Linux/UNIX (Amazon VPC)``

  
  *   ``Windows``

  
  *   ``Windows (Amazon VPC)``

  

  

``--filters`` (list)


  One or more filters.

   

   
  * ``availability-zone`` - The Availability Zone where the Reserved Instance can be used. 
   
  * ``duration`` - The duration of the Reserved Instance (for example, one year or three years), in seconds (``31536000`` | ``94608000`` ). 
   
  * ``fixed-price`` - The purchase price of the Reserved Instance (for example, 9800.0). 
   
  * ``instance-type`` - The instance type that is covered by the reservation. 
   
  * ``marketplace`` - Set to ``true`` to show only Reserved Instance Marketplace offerings. When this filter is not used, which is the default behavior, all offerings from both AWS and the Reserved Instance Marketplace are listed. 
   
  * ``product-description`` - The Reserved Instance product platform description. Instances that include ``(Amazon VPC)`` in the product platform description will only be displayed to EC2-Classic account holders and are for use with Amazon VPC. (``Linux/UNIX`` | ``Linux/UNIX (Amazon VPC)`` | ``SUSE Linux`` | ``SUSE Linux (Amazon VPC)`` | ``Red Hat Enterprise Linux`` | ``Red Hat Enterprise Linux (Amazon VPC)`` | ``Windows`` | ``Windows (Amazon VPC)`` | ``Windows with SQL Server Standard`` | ``Windows with SQL Server Standard (Amazon VPC)`` | ``Windows with SQL Server Web`` | ``Windows with SQL Server Web (Amazon VPC)`` | ``Windows with SQL Server Enterprise`` | ``Windows with SQL Server Enterprise (Amazon VPC)`` )  
   
  * ``reserved-instances-offering-id`` - The Reserved Instances offering ID. 
   
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



``--instance-tenancy`` (string)


  The tenancy of the instances covered by the reservation. A Reserved Instance with a tenancy of ``dedicated`` is applied to instances that run in a VPC on single-tenant hardware (i.e., Dedicated Instances).

   

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

  

  

``--include-marketplace`` | ``--no-include-marketplace`` (boolean)


  Include Reserved Instance Marketplace offerings in the response.

  

``--min-duration`` (long)


  The minimum duration (in seconds) to filter when searching for offerings.

   

  Default: 2592000 (1 month)

  

``--max-duration`` (long)


  The maximum duration (in seconds) to filter when searching for offerings.

   

  Default: 94608000 (3 years)

  

``--max-instance-count`` (integer)


  The maximum number of instances to filter when searching for offerings.

   

  Default: 20

  

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

    

    ReservedInstancesOfferingId -> (string)

      

      The ID of the Reserved Instance offering.

      

      

    InstanceType -> (string)

      

      The instance type on which the Reserved Instance can be used.

      

      

    AvailabilityZone -> (string)

      

      The Availability Zone in which the Reserved Instance can be used.

      

      

    Duration -> (long)

      

      The duration of the Reserved Instance, in seconds.

      

      

    UsagePrice -> (float)

      

      The usage price of the Reserved Instance, per hour.

      

      

    FixedPrice -> (float)

      

      The purchase price of the Reserved Instance.

      

      

    ProductDescription -> (string)

      

      The Reserved Instance product platform description.

      

      

    InstanceTenancy -> (string)

      

      The tenancy of the instance.

      

      

    CurrencyCode -> (string)

      

      The currency of the Reserved Instance offering you are purchasing. It's specified using ISO 4217 standard currency codes. At this time, the only supported currency is ``USD`` .

      

      

    OfferingType -> (string)

      

      The Reserved Instance offering type.

      

      

    RecurringCharges -> (list)

      

      The recurring charge tag assigned to the resource.

      

      (structure)

        

        Describes a recurring charge.

        

        Frequency -> (string)

          

          The frequency of the recurring charge.

          

          

        Amount -> (double)

          

          The amount of the recurring charge.

          

          

        

      

    Marketplace -> (boolean)

      

      Indicates whether the offering is available through the Reserved Instance Marketplace (resale) or AWS. If it's a Reserved Instance Marketplace offering, this is ``true`` .

      

      

    PricingDetails -> (list)

      

      The pricing details of the Reserved Instance offering.

      

      (structure)

        

        Describes a Reserved Instance offering.

        

        Price -> (double)

          

          The price per instance.

          

          

        Count -> (integer)

          

          The number of reservations available for the price.

          

          

        

      

    

  

NextToken -> (string)

  

  The token to use to retrieve the next page of results. This value is ``null`` when there are no more results to return.

  

  



.. _Instance Types: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-types.html
.. _Reserved Instance Marketplace: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ri-market-general.html
