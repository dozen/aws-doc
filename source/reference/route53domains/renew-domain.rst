[ :ref:`aws <cli:aws>` . :ref:`route53domains <cli:aws route53domains>` ]

.. _cli:aws route53domains renew-domain:


************
renew-domain
************



===========
Description
===========



This operation renews a domain for the specified number of years. The cost of renewing your domain is billed to your AWS account.

 

We recommend that you renew your domain several weeks before the expiration date. Some TLD registries delete domains before the expiration date if you haven't renewed far enough in advance. For more information about renewing domain registration, see `Renewing Registration for a Domain <http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/domain-renew.html>`_ in the Amazon Route 53 Developer Guide.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53domains-2014-05-15/RenewDomain>`_


========
Synopsis
========

::

    renew-domain
  --domain-name <value>
  [--duration-in-years <value>]
  --current-expiry-year <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--domain-name`` (string)


  The name of the domain that you want to renew.

  

``--duration-in-years`` (integer)


  The number of years that you want to renew the domain for. The maximum number of years depends on the top-level domain. For the range of valid values for your domain, see `Domains that You Can Register with Amazon Route 53 <http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/registrar-tld-list.html>`_ in the *Amazon Route 53 Developer Guide* .

   

  Default: 1

  

``--current-expiry-year`` (integer)


  The year when the registration for the domain is set to expire. This value must match the current expiration date for the domain.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

OperationId -> (string)

  

  The identifier for tracking the progress of the request. To use this ID to query the operation status, use  get-operation-detail .

  

  

