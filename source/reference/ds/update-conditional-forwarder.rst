[ :ref:`aws <cli:aws>` . :ref:`ds <cli:aws ds>` ]

.. _cli:aws ds update-conditional-forwarder:


****************************
update-conditional-forwarder
****************************



===========
Description
===========



Updates a conditional forwarder that has been set up for your AWS directory.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ds-2015-04-16/UpdateConditionalForwarder>`_


========
Synopsis
========

::

    update-conditional-forwarder
  --directory-id <value>
  --remote-domain-name <value>
  --dns-ip-addrs <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--directory-id`` (string)


  The directory ID of the AWS directory for which to update the conditional forwarder.

  

``--remote-domain-name`` (string)


  The fully qualified domain name (FQDN) of the remote domain with which you will set up a trust relationship.

  

``--dns-ip-addrs`` (list)


  The updated IP addresses of the remote DNS server associated with the conditional forwarder.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

