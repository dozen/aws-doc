[ :ref:`aws <cli:aws>` . :ref:`meteringmarketplace <cli:aws meteringmarketplace>` ]

.. _cli:aws meteringmarketplace resolve-customer:


****************
resolve-customer
****************



===========
Description
===========



resolve-customer is called by a SaaS application during the registration process. When a buyer visits your website during the registration process, the buyer submits a registration token through their browser. The registration token is resolved through this API to obtain a CustomerIdentifier and product code.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/meteringmarketplace-2016-01-14/ResolveCustomer>`_


========
Synopsis
========

::

    resolve-customer
  --registration-token <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--registration-token`` (string)


  When a buyer visits your website during the registration process, the buyer submits a registration token through the browser. The registration token is resolved to obtain a CustomerIdentifier and product code.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

CustomerIdentifier -> (string)

  

  The CustomerIdentifier is used to identify an individual customer in your application. Calls to batch-meter-usage require CustomerIdentifiers for each UsageRecord.

  

  

ProductCode -> (string)

  

  The product code is returned to confirm that the buyer is registering for your product. Subsequent batch-meter-usage calls should be made using this product code.

  

  

