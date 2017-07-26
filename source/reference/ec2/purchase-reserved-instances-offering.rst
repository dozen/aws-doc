[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 purchase-reserved-instances-offering:


************************************
purchase-reserved-instances-offering
************************************



===========
Description
===========



Purchases a Reserved Instance for use with your account. With Reserved Instances, you pay a lower hourly rate compared to On-Demand instance pricing.

 

Use  describe-reserved-instances-offerings to get a list of Reserved Instance offerings that match your specifications. After you've purchased a Reserved Instance, you can check for your new Reserved Instance with  describe-reserved-instances .

 

For more information, see `Reserved Instances <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts-on-demand-reserved-instances.html>`_ and `Reserved Instance Marketplace <http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ri-market-general.html>`_ in the *Amazon Elastic Compute Cloud User Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/PurchaseReservedInstancesOffering>`_


========
Synopsis
========

::

    purchase-reserved-instances-offering
  --instance-count <value>
  --reserved-instances-offering-id <value>
  [--dry-run | --no-dry-run]
  [--limit-price <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--instance-count`` (integer)


  The number of Reserved Instances to purchase.

  

``--reserved-instances-offering-id`` (string)


  The ID of the Reserved Instance offering to purchase.

  

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

  

  

