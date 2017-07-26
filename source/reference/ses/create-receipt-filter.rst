[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses create-receipt-filter:


*********************
create-receipt-filter
*********************



===========
Description
===========



Creates a new IP address filter.

 

For information about setting up IP address filters, see the `Amazon SES Developer Guide`_ .

 

This action is throttled at one request per second.



========
Synopsis
========

::

    create-receipt-filter
  --filter <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--filter`` (structure)


  A data structure that describes the IP address filter to create, which consists of a name, an IP address range, and whether to allow or block mail from it.

  



Shorthand Syntax::

    Name=string,IpFilter={Policy=string,Cidr=string}




JSON Syntax::

  {
    "Name": "string",
    "IpFilter": {
      "Policy": "Block"|"Allow",
      "Cidr": "string"
    }
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======



.. _Amazon SES Developer Guide: http://docs.aws.amazon.com/ses/latest/DeveloperGuide/receiving-email-ip-filters.html
