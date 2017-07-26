[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 purchase-reserved-instances-offering:


************************************
purchase-reserved-instances-offering
************************************



===========
Description
===========



Purchases a Reserved Instance for use with your account. With Reserved Instances, you obtain a capacity reservation for a certain instance configuration over a specified period of time and pay a lower hourly rate compared to On-Demand instance pricing.

 

Use  describe-reserved-instances-offerings to get a list of Reserved Instance offerings that match your specifications. After you've purchased a Reserved Instance, you can check for your new Reserved Instance with  describe-reserved-instances .

 

For more information, see `Reserved Instances`_ and `Reserved Instance Marketplace`_ in the *Amazon Elastic Compute Cloud User Guide* .



========
Synopsis
========

::

    purchase-reserved-instances-offering
  [--dry-run | --no-dry-run]
  --reserved-instances-offering-id <value>
  --instance-count <value>
  [--limit-price <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--reserved-instances-offering-id`` (string)


  The ID of the Reserved Instance offering to purchase.

  

``--instance-count`` (integer)


  The number of Reserved Instances to purchase.

  

``--limit-price`` (structure)


  Specified for Reserved Instance Marketplace offerings to limit the total order and ensure that the Reserved Instances are not purchased at unexpected prices.

  



Shorthand Syntax::

    Amount=double,CurrencyCode=string




JSON Syntax::

  {
    "Amount": double,
    "CurrencyCode": "USD"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To purchase a Reserved Instance offering**

This example command illustrates a purchase of a Reserved Instances offering, specifying an offering ID and instance count.

Command::

  aws ec2 purchase-reserved-instances-offering --reserved-instances-offering-id ec06327e-dd07-46ee-9398-75b5fexample --instance-count 3
  
  
Output::

  {
    "ReservedInstancesId": "af9f760e-6f91-4559-85f7-4980eexample"
  }        
        



======
Output
======

ReservedInstancesId -> (string)

  

  The IDs of the purchased Reserved Instances.

  

  



.. _Reserved Instance Marketplace: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ri-market-general.html
.. _Reserved Instances: http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts-on-demand-reserved-instances.html
