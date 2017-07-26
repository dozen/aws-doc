[ :ref:`aws <cli:aws>` . :ref:`ds <cli:aws ds>` ]

.. _cli:aws ds describe-conditional-forwarders:


*******************************
describe-conditional-forwarders
*******************************



===========
Description
===========



Obtains information about the conditional forwarders for this account.

 

If no input parameters are provided for RemoteDomainNames, this request describes all conditional forwarders for the specified directory ID.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ds-2015-04-16/DescribeConditionalForwarders>`_


========
Synopsis
========

::

    describe-conditional-forwarders
  --directory-id <value>
  [--remote-domain-names <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--directory-id`` (string)


  The directory ID for which to get the list of associated conditional forwarders.

  

``--remote-domain-names`` (list)


  The fully qualified domain names (FQDN) of the remote domains for which to get the list of associated conditional forwarders. If this member is null, all conditional forwarders are returned.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ConditionalForwarders -> (list)

  

  The list of conditional forwarders that have been created.

  

  (structure)

    

    Points to a remote domain with which you are setting up a trust relationship. Conditional forwarders are required in order to set up a trust relationship with another domain.

    

    RemoteDomainName -> (string)

      

      The fully qualified domain name (FQDN) of the remote domains pointed to by the conditional forwarder.

      

      

    DnsIpAddrs -> (list)

      

      The IP addresses of the remote DNS server associated with RemoteDomainName. This is the IP address of the DNS server that your conditional forwarder points to.

      

      (string)

        

        

      

    ReplicationScope -> (string)

      

      The replication scope of the conditional forwarder. The only allowed value is ``Domain`` , which will replicate the conditional forwarder to all of the domain controllers for your AWS directory.

      

      

    

  

