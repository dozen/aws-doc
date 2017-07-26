[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses list-receipt-filters:


********************
list-receipt-filters
********************



===========
Description
===========



Lists the IP address filters associated with your account.

 

For information about managing IP address filters, see the `Amazon SES Developer Guide`_ .

 

This action is throttled at one request per second.



========
Synopsis
========

::

    list-receipt-filters
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

Filters -> (list)

  

  A list of IP address filter data structures, which each consist of a name, an IP address range, and whether to allow or block mail from it.

  

  (structure)

    

    A receipt IP address filter enables you to specify whether to accept or reject mail originating from an IP address or range of IP addresses.

     

    For information about setting up IP address filters, see the `Amazon SES Developer Guide`_ .

    

    Name -> (string)

      

      The name of the IP address filter. The name must:

       

       
      * Contain only ASCII letters (a-z, A-Z), numbers (0-9), periods (.), underscores (_), or dashes (-).
       
      * Start and end with a letter or number.
       
      * Contain less than 64 characters.
       

      

      

    IpFilter -> (structure)

      

      A structure that provides the IP addresses to block or allow, and whether to block or allow incoming mail from them.

      

      Policy -> (string)

        

        Indicates whether to block or allow incoming mail from the specified IP addresses.

        

        

      Cidr -> (string)

        

        A single IP address or a range of IP addresses that you want to block or allow, specified in Classless Inter-Domain Routing (CIDR) notation. An example of a single email address is 10.0.0.1. An example of a range of IP addresses is 10.0.0.1/24. For more information about CIDR notation, see `RFC 2317`_ .

        

        

      

    

  



.. _RFC 2317: https://tools.ietf.org/html/rfc2317
.. _Amazon SES Developer Guide: http://docs.aws.amazon.com/ses/latest/DeveloperGuide/receiving-email-ip-filters.html
