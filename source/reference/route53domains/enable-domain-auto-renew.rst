[ :ref:`aws <cli:aws>` . :ref:`route53domains <cli:aws route53domains>` ]

.. _cli:aws route53domains enable-domain-auto-renew:


************************
enable-domain-auto-renew
************************



===========
Description
===========



This operation configures Amazon Route 53 to automatically renew the specified domain before the domain registration expires. The cost of renewing your domain registration is billed to your AWS account.

 

The period during which you can renew a domain name varies by TLD. For a list of TLDs and their renewal policies, see `"Renewal, restoration, and deletion times"`_ on the website for our registrar partner, Gandi. Route 53 requires that you renew before the end of the renewal period that is listed on the Gandi website so we can complete processing before the deadline.



========
Synopsis
========

::

    enable-domain-auto-renew
  --domain-name <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--domain-name`` (string)


``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======



.. _"Renewal, restoration, and deletion times": http://wiki.gandi.net/en/domains/renew#renewal_restoration_and_deletion_times
