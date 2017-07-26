[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-reserved-instances:


***************************
describe-reserved-instances
***************************



===========
Description
===========



Describes one or more of the Reserved Instances that you purchased.

 

For more information about Reserved Instances, see `Reserved Instances`_ in the *Amazon Elastic Compute Cloud User Guide* .



========
Synopsis
========

::

    describe-reserved-instances
  [--dry-run | --no-dry-run]
  [--reserved-instances-ids <value>]
  [--filters <value>]
  [--offering-type <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--reserved-instances-ids`` (list)


  One or more Reserved Instance IDs.

   

  Default: Describes all your Reserved Instances, or only those otherwise specified.

  



Syntax::

  "string" "string" ...



``--filters`` (list)


  One or more filters.

   

   
  * ``availability-zone`` - The Availability Zone where the Reserved Instance can be used. 
   
  * ``duration`` - The duration of the Reserved Instance (one year or three years), in seconds (``31536000`` | ``94608000`` ). 
   
  * ``end`` - The time when the Reserved Instance expires (for example, 2015-08-07T11:54:42.000Z). 
   
  * ``fixed-price`` - The purchase price of the Reserved Instance (for example, 9800.0). 
   
  * ``instance-type`` - The instance type that is covered by the reservation. 
   
  * ``product-description`` - The Reserved Instance product platform description. Instances that include ``(Amazon VPC)`` in the product platform description will only be displayed to EC2-Classic account holders and are for use with Amazon VPC (``Linux/UNIX`` | ``Linux/UNIX (Amazon VPC)`` | ``SUSE Linux`` | ``SUSE Linux (Amazon VPC)`` | ``Red Hat Enterprise Linux`` | ``Red Hat Enterprise Linux (Amazon VPC)`` | ``Windows`` | ``Windows (Amazon VPC)`` | ``Windows with SQL Server Standard`` | ``Windows with SQL Server Standard (Amazon VPC)`` | ``Windows with SQL Server Web`` | ``Windows with SQL Server Web (Amazon VPC)`` | ``Windows with SQL Server Enterprise`` | ``Windows with SQL Server Enterprise (Amazon VPC)`` ). 
   
  * ``reserved-instances-id`` - The ID of the Reserved Instance. 
   
  * ``start`` - The time at which the Reserved Instance purchase request was placed (for example, 2014-08-07T11:54:42.000Z). 
   
  * ``state`` - The state of the Reserved Instance (``payment-pending`` | ``active`` | ``payment-failed`` | ``retired`` ). 
   
  * ``tag`` :*key* =*value* - The key/value combination of a tag assigned to the resource. 
   
  * ``tag-key`` - The key of a tag assigned to the resource. This filter is independent of the ``tag-value`` filter. For example, if you use both the filter "tag-key=Purpose" and the filter "tag-value=X", you get any resources assigned both the tag key Purpose (regardless of what the tag's value is), and the tag value X (regardless of what the tag's key is). If you want to list only resources where Purpose is X, see the ``tag`` :*key* =*value* filter. 
   
  * ``tag-value`` - The value of a tag assigned to the resource. This filter is independent of the ``tag-key`` filter. 
   
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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To describe your Reserved Instances**

This example command describes the Reserved Instances that you own.

Command::

  aws ec2 describe-reserved-instances

Output::

  {
    "ReservedInstances": [
        {
            "ReservedInstancesId": "b847fa93-e282-4f55-b59a-1342fexample",
            "OfferingType": "No Upfront",
            "AvailabilityZone": "us-west-1c",
            "End": "2016-08-14T21:34:34.000Z",
            "ProductDescription": "Linux/UNIX",
            "UsagePrice": 0.00,
            "RecurringCharges": [
                {
                    "Amount": 0.104,
                    "Frequency": "Hourly"
                }
            ],
            "Start": "2015-08-15T21:34:35.086Z",
            "State": "active",
            "FixedPrice": 0.0,
            "CurrencyCode": "USD",
            "Duration": 31536000,
            "InstanceTenancy": "default",
            "InstanceType": "m3.medium",
            "InstanceCount": 2
        },
        ...
    ]
  }

**To describe your Reserved Instances using filters**

This example filters the response to include only three-year, t2.micro Linux/UNIX Reserved Instances in us-west-1c.

Command::
    
    aws ec2 describe-reserved-instances --filters Name=duration,Values=94608000 Name=instance-type,Values=t2.micro Name=product-description,Values=Linux/UNIX Name=availability-zone,Values=us-east-1e

Output::

  {
      "ReservedInstances": [
          {
              "ReservedInstancesId": "f127bd27-edb7-44c9-a0eb-0d7e09259af0",
              "OfferingType": "All Upfront",
              "AvailabilityZone": "us-east-1e",
              "End": "2018-03-26T21:34:34.000Z",
              "ProductDescription": "Linux/UNIX",
              "UsagePrice": 0.00,
              "RecurringCharges": [],
              "Start": "2015-03-27T21:34:35.848Z",
              "State": "active",
              "FixedPrice": 151.0,
              "CurrencyCode": "USD",
              "Duration": 94608000,
              "InstanceTenancy": "default",
              "InstanceType": "t2.micro",
              "InstanceCount": 1
          }
      ]
  }

For more information, see `Using Amazon EC2 Instances`_ in the *AWS Command Line Interface User Guide*.

.. _`Using Amazon EC2 Instances`: http://docs.aws.amazon.com/cli/latest/userguide/cli-ec2-launch.html



======
Output
======

ReservedInstances -> (list)

  

  A list of Reserved Instances.

  

  (structure)

    

    Describes a Reserved Instance.

    

    ReservedInstancesId -> (string)

      

      The ID of the Reserved Instance.

      

      

    InstanceType -> (string)

      

      The instance type on which the Reserved Instance can be used.

      

      

    AvailabilityZone -> (string)

      

      The Availability Zone in which the Reserved Instance can be used.

      

      

    Start -> (timestamp)

      

      The date and time the Reserved Instance started.

      

      

    End -> (timestamp)

      

      The time when the Reserved Instance expires.

      

      

    Duration -> (long)

      

      The duration of the Reserved Instance, in seconds.

      

      

    UsagePrice -> (float)

      

      The usage price of the Reserved Instance, per hour.

      

      

    FixedPrice -> (float)

      

      The purchase price of the Reserved Instance.

      

      

    InstanceCount -> (integer)

      

      The number of reservations purchased.

      

      

    ProductDescription -> (string)

      

      The Reserved Instance product platform description.

      

      

    State -> (string)

      

      The state of the Reserved Instance purchase.

      

      

    Tags -> (list)

      

      Any tags assigned to the resource.

      

      (structure)

        

        Describes a tag.

        

        Key -> (string)

          

          The key of the tag. 

           

          Constraints: Tag keys are case-sensitive and accept a maximum of 127 Unicode characters. May not begin with ``aws:`` 

          

          

        Value -> (string)

          

          The value of the tag.

           

          Constraints: Tag values are case-sensitive and accept a maximum of 255 Unicode characters.

          

          

        

      

    InstanceTenancy -> (string)

      

      The tenancy of the instance.

      

      

    CurrencyCode -> (string)

      

      The currency of the Reserved Instance. It's specified using ISO 4217 standard currency codes. At this time, the only supported currency is ``USD`` .

      

      

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

          

          

        

      

    

  



.. _Reserved Instances: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts-on-demand-reserved-instances.html
