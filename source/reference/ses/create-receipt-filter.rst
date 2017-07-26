[ :ref:`aws <cli:aws>` . :ref:`ses <cli:aws ses>` ]

.. _cli:aws ses create-receipt-filter:


*********************
create-receipt-filter
*********************



===========
Description
===========



Creates a new IP address filter.

 

For information about setting up IP address filters, see the `Amazon SES Developer Guide <http://docs.aws.amazon.com/ses/latest/DeveloperGuide/receiving-email-ip-filters.html>`_ .

 

This action is throttled at one request per second.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/email-2010-12-01/CreateReceiptFilter>`_


========
Synopsis
========

::

    create-receipt-filter
  --filter <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

