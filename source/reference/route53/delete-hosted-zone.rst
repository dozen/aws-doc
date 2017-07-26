[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 delete-hosted-zone:


******************
delete-hosted-zone
******************



===========
Description
===========



Deletes a hosted zone.

 

.. warning::

   

  If the name servers for the hosted zone are associated with a domain and if you want to make the domain unavailable on the Internet, we recommend that you delete the name servers from the domain to prevent future DNS queries from possibly being misrouted. If the domain is registered with Amazon Route 53, see ``UpdateDomainNameservers`` . If the domain is registered with another registrar, use the method provided by the registrar to delete name servers for the domain.

   

  Some domain registries don't allow you to remove all of the name servers for a domain. If the registry for your domain requires one or more name servers, we recommend that you delete the hosted zone only if you transfer DNS service to another service provider, and you replace the name servers for the domain with name servers from the new provider.

   

 

You can delete a hosted zone only if it contains only the default SOA record and NS resource record sets. If the hosted zone contains other resource record sets, you must delete them before you can delete the hosted zone. If you try to delete a hosted zone that contains other resource record sets, the request fails, and Amazon Route 53 returns a ``HostedZoneNotEmpty`` error. For information about deleting records from your hosted zone, see  change-resource-record-sets .

 

To verify that the hosted zone has been deleted, do one of the following:

 

 
* Use the ``get-hosted-zone`` action to request information about the hosted zone. 
 
* Use the ``list-hosted-zones`` action to get a list of the hosted zones associated with the current AWS account. 
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53-2013-04-01/DeleteHostedZone>`_


========
Synopsis
========

::

    delete-hosted-zone
  --id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--id`` (string)


  The ID of the hosted zone you want to delete.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To delete a hosted zone**

The following ``delete-hosted-zone`` command deletes the hosted zone with an ``id`` of  ``Z36KTIQEXAMPLE``::

  aws route53 delete-hosted-zone --id Z36KTIQEXAMPLE



======
Output
======

ChangeInfo -> (structure)

  

  A complex type that contains the ID, the status, and the date and time of a request to delete a hosted zone.

  

  Id -> (string)

    

    The ID of the request.

    

    

  Status -> (string)

    

    The current state of the request. ``PENDING`` indicates that this request has not yet been applied to all Amazon Route 53 DNS servers.

    

    

  SubmittedAt -> (timestamp)

    

    The date and time that the change request was submitted in `ISO 8601 format <https://en.wikipedia.org/wiki/ISO_8601>`_ and Coordinated Universal Time (UTC). For example, the value ``2017-03-27T17:48:16.751Z`` represents March 27, 2017 at 17:48:16.751 UTC.

    

    

  Comment -> (string)

    

    A complex type that describes change information about changes made to your hosted zone.

     

    This element contains an ID that you use when performing a  get-change action to get detailed information about the change.

    

    

  

