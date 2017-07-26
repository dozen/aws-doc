[ :ref:`aws <cli:aws>` . :ref:`route53domains <cli:aws route53domains>` ]

.. _cli:aws route53domains enable-domain-auto-renew:


************************
enable-domain-auto-renew
************************



===========
Description
===========



This operation configures Amazon Route 53 to automatically renew the specified domain before the domain registration expires. The cost of renewing your domain registration is billed to your AWS account.

 

The period during which you can renew a domain name varies by TLD. For a list of TLDs and their renewal policies, see `"Renewal, restoration, and deletion times" <http://wiki.gandi.net/en/domains/renew#renewal_restoration_and_deletion_times>`_ on the website for our registrar partner, Gandi. Route 53 requires that you renew before the end of the renewal period that is listed on the Gandi website so we can complete processing before the deadline.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53domains-2014-05-15/EnableDomainAutoRenew>`_


========
Synopsis
========

::

    enable-domain-auto-renew
  --domain-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--domain-name`` (string)


  The name of the domain that you want to enable automatic renewal for.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

