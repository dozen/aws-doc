[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 get-checker-ip-ranges:


*********************
get-checker-ip-ranges
*********************



===========
Description
===========



To retrieve a list of the IP ranges used by Amazon Route 53 health checkers to check the health of your resources, send a ``GET`` request to the ``/*Route 53 API version* /checkeripranges`` resource. You can use these IP addresses to configure router and firewall rules to allow health checkers to check the health of your resources.



========
Synopsis
========

::

    get-checker-ip-ranges
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

CheckerIpRanges -> (list)

  

  A complex type that contains sorted list of IP ranges in CIDR format for Amazon Route 53 health checkers.

  

  (string)

    

    

  

