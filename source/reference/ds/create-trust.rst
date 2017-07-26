[ :ref:`aws <cli:aws>` . :ref:`ds <cli:aws ds>` ]

.. _cli:aws ds create-trust:


************
create-trust
************



===========
Description
===========



AWS Directory Service for Microsoft Active Directory allows you to configure trust relationships. For example, you can establish a trust between your Microsoft AD in the AWS cloud, and your existing on-premises Microsoft Active Directory. This would allow you to provide users and groups access to resources in either domain, with a single set of credentials.

 

This action initiates the creation of the AWS side of a trust relationship between a Microsoft AD in the AWS cloud and an external domain.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ds-2015-04-16/CreateTrust>`_


========
Synopsis
========

::

    create-trust
  --directory-id <value>
  --remote-domain-name <value>
  --trust-password <value>
  --trust-direction <value>
  [--trust-type <value>]
  [--conditional-forwarder-ip-addrs <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--directory-id`` (string)


  The Directory ID of the Microsoft AD in the AWS cloud for which to establish the trust relationship.

  

``--remote-domain-name`` (string)


  The Fully Qualified Domain Name (FQDN) of the external domain for which to create the trust relationship.

  

``--trust-password`` (string)


  The trust password. The must be the same password that was used when creating the trust relationship on the external domain.

  

``--trust-direction`` (string)


  The direction of the trust relationship.

  

  Possible values:

  
  *   ``One-Way: Outgoing``

  
  *   ``One-Way: Incoming``

  
  *   ``Two-Way``

  

  

``--trust-type`` (string)


  The trust relationship type.

  

  Possible values:

  
  *   ``Forest``

  

  

``--conditional-forwarder-ip-addrs`` (list)


  The IP addresses of the remote DNS server associated with RemoteDomainName.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

TrustId -> (string)

  

  A unique identifier for the trust relationship that was created.

  

  

