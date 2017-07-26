[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-spot-price-history:


***************************
describe-spot-price-history
***************************



===========
Description
===========



Describes the Spot price history. The prices returned are listed in chronological order, from the oldest to the most recent, for up to the past 90 days. For more information, see `Spot Instance Pricing History`_ in the *Amazon Elastic Compute Cloud User Guide* .

 

When you specify a start and end time, this operation returns the prices of the instance types within the time range that you specified and the time when the price changed. The price is valid within the time period that you specified; the response merely indicates the last time that the price changed.



``describe-spot-price-history`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``SpotPriceHistory``


========
Synopsis
========

::

    describe-spot-price-history
  [--dry-run | --no-dry-run]
  [--start-time <value>]
  [--end-time <value>]
  [--instance-types <value>]
  [--product-descriptions <value>]
  [--filters <value>]
  [--availability-zone <value>]
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

  

``--start-time`` (timestamp)


  The date and time, up to the past 90 days, from which to start retrieving the price history data, in UTC format (for example, *YYYY* -*MM* -*DD* T*HH* :*MM* :*SS* Z).

  

``--end-time`` (timestamp)


  The date and time, up to the current date, from which to stop retrieving the price history data, in UTC format (for example, *YYYY* -*MM* -*DD* T*HH* :*MM* :*SS* Z).

  

``--instance-types`` (list)


  Filters the results by the specified instance types.

  



Syntax::

  "string" "string" ...

  Where valid values are:
    t1.micro
    m1.small
    m1.medium
    m1.large
    m1.xlarge
    m3.medium
    m3.large
    m3.xlarge
    m3.2xlarge
    m4.large
    m4.xlarge
    m4.2xlarge
    m4.4xlarge
    m4.10xlarge
    t2.nano
    t2.micro
    t2.small
    t2.medium
    t2.large
    m2.xlarge
    m2.2xlarge
    m2.4xlarge
    cr1.8xlarge
    i2.xlarge
    i2.2xlarge
    i2.4xlarge
    i2.8xlarge
    hi1.4xlarge
    hs1.8xlarge
    c1.medium
    c1.xlarge
    c3.large
    c3.xlarge
    c3.2xlarge
    c3.4xlarge
    c3.8xlarge
    c4.large
    c4.xlarge
    c4.2xlarge
    c4.4xlarge
    c4.8xlarge
    cc1.4xlarge
    cc2.8xlarge
    g2.2xlarge
    cg1.4xlarge
    r3.large
    r3.xlarge
    r3.2xlarge
    r3.4xlarge
    r3.8xlarge
    d2.xlarge
    d2.2xlarge
    d2.4xlarge
    d2.8xlarge





``--product-descriptions`` (list)


  Filters the results by the specified basic product descriptions.

  



Syntax::

  "string" "string" ...



``--filters`` (list)


  One or more filters.

   

   
  * ``availability-zone`` - The Availability Zone for which prices should be returned. 
   
  * ``instance-type`` - The type of instance (for example, ``m3.medium`` ). 
   
  * ``product-description`` - The product description for the Spot price (``Linux/UNIX`` | ``SUSE Linux`` | ``Windows`` | ``Linux/UNIX (Amazon VPC)`` | ``SUSE Linux (Amazon VPC)`` | ``Windows (Amazon VPC)`` ). 
   
  * ``spot-price`` - The Spot price. The value must match exactly (or use wildcards; greater than or less than comparison is not supported). 
   
  * ``timestamp`` - The timestamp of the Spot price history, in UTC format (for example, *YYYY* -*MM* -*DD* T*HH* :*MM* :*SS* Z). You can use wildcards (* and ?). Greater than or less than comparison is not supported. 
   

  



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



``--availability-zone`` (string)


  Filters the results by the specified Availability Zone.

  

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

**To describe Spot price history**

This example command returns the Spot Price history for m1.xlarge instances for a particular day in January.

Command::

  aws ec2 describe-spot-price-history --instance-types m1.xlarge --start-time 2014-01-06T07:08:09 --end-time 2014-01-06T08:09:10

Output::

  {
    "SpotPriceHistory": [
            {
                "Timestamp": "2014-01-06T07:10:55.000Z",
                "ProductDescription": "SUSE Linux",
                "InstanceType": "m1.xlarge",
                "SpotPrice": "0.087000",
                "AvailabilityZone": "us-west-1b"
            },
            {
                "Timestamp": "2014-01-06T07:10:55.000Z",
                "ProductDescription": "SUSE Linux",
                "InstanceType": "m1.xlarge",
                "SpotPrice": "0.087000",
                "AvailabilityZone": "us-west-1c"
            },
            {
                "Timestamp": "2014-01-06T05:42:36.000Z",
                "ProductDescription": "SUSE Linux (Amazon VPC)",
                "InstanceType": "m1.xlarge",
                "SpotPrice": "0.087000",
                "AvailabilityZone": "us-west-1a"
        },
        ...
  }


**To describe Spot price history for Linux/UNIX Amazon VPC**

This example command returns the Spot Price history for m1.xlarge, Linux/UNIX Amazon VPC instances for a particular day in January.

Command::

  aws ec2 describe-spot-price-history --instance-types m1.xlarge --product-description "Linux/UNIX (Amazon VPC)" --start-time 2014-01-06T07:08:09 --end-time 2014-01-06T08:09:10

Output::

  {
    "SpotPriceHistory": [
        {
            "Timestamp": "2014-01-06T04:32:53.000Z",
            "ProductDescription": "Linux/UNIX (Amazon VPC)",
            "InstanceType": "m1.xlarge",
            "SpotPrice": "0.080000",
            "AvailabilityZone": "us-west-1a"
        },
        {
            "Timestamp": "2014-01-05T11:28:26.000Z",
            "ProductDescription": "Linux/UNIX (Amazon VPC)",
            "InstanceType": "m1.xlarge",
            "SpotPrice": "0.080000",
            "AvailabilityZone": "us-west-1c"
        }
    ]
  }

======
Output
======

SpotPriceHistory -> (list)

  

  The historical Spot prices.

  

  (structure)

    

    Describes the maximum hourly price (bid) for any Spot instance launched to fulfill the request.

    

    InstanceType -> (string)

      

      The instance type.

      

      

    ProductDescription -> (string)

      

      A general description of the AMI.

      

      

    SpotPrice -> (string)

      

      The maximum price (bid) that you are willing to pay for a Spot instance.

      

      

    Timestamp -> (timestamp)

      

      The date and time the request was created, in UTC format (for example, *YYYY* -*MM* -*DD* T*HH* :*MM* :*SS* Z).

      

      

    AvailabilityZone -> (string)

      

      The Availability Zone.

      

      

    

  

NextToken -> (string)

  

  The token required to retrieve the next set of results. This value is ``null`` when there are no more results to return.

  

  



.. _Spot Instance Pricing History: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-spot-instances-history.html
