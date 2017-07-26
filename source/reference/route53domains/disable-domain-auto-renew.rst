[ :ref:`aws <cli:aws>` . :ref:`route53domains <cli:aws route53domains>` ]

.. _cli:aws route53domains disable-domain-auto-renew:


*************************
disable-domain-auto-renew
*************************



===========
Description
===========



This operation disables automatic renewal of domain registration for the specified domain.

 

.. note::

  Caution! Amazon Route 53 doesn't have a manual renewal process, so if you disable automatic renewal, registration for the domain will not be renewed when the expiration date passes, and you will lose control of the domain name.



========
Synopsis
========

::

    disable-domain-auto-renew
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

