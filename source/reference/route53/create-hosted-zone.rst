[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 create-hosted-zone:


******************
create-hosted-zone
******************



===========
Description
===========



Creates a new public hosted zone, which you use to specify how the Domain Name System (DNS) routes traffic on the Internet for a domain, such as example.com, and its subdomains. 

 

.. warning::

   

  You can't convert a public hosted zones to a private hosted zone or vice versa. Instead, you must create a new hosted zone with the same name and create new resource record sets.

   

 

For more information about charges for hosted zones, see `Amazon Route 53 Pricing <http://aws.amazon.com/route53/pricing/>`_ .

 

Note the following:

 

 
* You can't create a hosted zone for a top-level domain (TLD). 
 
* Amazon Route 53 automatically creates a default SOA record and four NS records for the zone. For more information about SOA and NS records, see `NS and SOA Records that Amazon Route 53 Creates for a Hosted Zone <http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/SOA-NSrecords.html>`_ in the *Amazon Route 53 Developer Guide* . If you want to use the same name servers for multiple hosted zones, you can optionally associate a reusable delegation set with the hosted zone. See the ``DelegationSetId`` element. 
 
* If your domain is registered with a registrar other than Amazon Route 53, you must update the name servers with your registrar to make Amazon Route 53 your DNS service. For more information, see `Configuring Amazon Route 53 as your DNS Service <http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/creating-migrating.html>`_ in the *Amazon Route 53 Developer Guide* .  
 

 

When you submit a ``create-hosted-zone`` request, the initial status of the hosted zone is ``PENDING`` . This means that the NS and SOA records are not yet available on all Amazon Route 53 DNS servers. When the NS and SOA records are available, the status of the zone changes to ``INSYNC`` .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53-2013-04-01/CreateHostedZone>`_


========
Synopsis
========

::

    create-hosted-zone
  --name <value>
  [--vpc <value>]
  --caller-reference <value>
  [--hosted-zone-config <value>]
  [--delegation-set-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--name`` (string)


  The name of the domain. For resource record types that include a domain name, specify a fully qualified domain name, for example, *www.example.com* . The trailing dot is optional; Amazon Route 53 assumes that the domain name is fully qualified. This means that Amazon Route 53 treats *www.example.com* (without a trailing dot) and *www.example.com.* (with a trailing dot) as identical.

   

  If you're creating a public hosted zone, this is the name you have registered with your DNS registrar. If your domain name is registered with a registrar other than Amazon Route 53, change the name servers for your domain to the set of ``NameServers`` that ``create-hosted-zone`` returns in ``DelegationSet`` .

  

``--vpc`` (structure)


  (Private hosted zones only) A complex type that contains information about the Amazon vpc that you're associating with this hosted zone.

   

  You can specify only one Amazon vpc when you create a private hosted zone. To associate additional Amazon VPCs with the hosted zone, use  associate-vpc-with-hosted-zone after you create a hosted zone.

  



Shorthand Syntax::

    VPCRegion=string,VPCId=string




JSON Syntax::

  {
    "VPCRegion": "us-east-1"|"us-east-2"|"us-west-1"|"us-west-2"|"eu-west-1"|"eu-west-2"|"eu-central-1"|"ap-southeast-1"|"ap-southeast-2"|"ap-south-1"|"ap-northeast-1"|"ap-northeast-2"|"sa-east-1"|"ca-central-1"|"cn-north-1",
    "VPCId": "string"
  }



``--caller-reference`` (string)


  A unique string that identifies the request and that allows failed ``create-hosted-zone`` requests to be retried without the risk of executing the operation twice. You must use a unique ``CallerReference`` string every time you submit a ``create-hosted-zone`` request. ``CallerReference`` can be any unique string, for example, a date/time stamp.

  

``--hosted-zone-config`` (structure)


  (Optional) A complex type that contains the following optional values:

   

   
  * For public and private hosted zones, an optional comment 
   
  * For private hosted zones, an optional ``PrivateZone`` element 
   

   

  If you don't specify a comment or the ``PrivateZone`` element, omit ``hosted-zone-config`` and the other elements.

  



Note do **not** include ``PrivateZone`` in this input structure. Its value is returned in the output to the command.



Shorthand Syntax::

    Comment=string,PrivateZone=boolean




JSON Syntax::

  {
    "Comment": "string",
    "PrivateZone": true|false
  }



``--delegation-set-id`` (string)


  If you want to associate a reusable delegation set with this hosted zone, the ID that Amazon Route 53 assigned to the reusable delegation set when you created it. For more information about reusable delegation sets, see  create-reusable-delegation-set .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a hosted zone**

The following ``create-hosted-zone`` command adds a hosted zone named ``example.com`` using the caller reference ``2014-04-01-18:47``. The optional comment includes a space, so it must be enclosed in quotation marks::

  aws route53 create-hosted-zone --name example.com --caller-reference 2014-04-01-18:47 --hosted-zone-config Comment="command-line version"

For more information, see `Working with Hosted Zones`_ in the *Amazon Route 53 Developer Guide*.

.. _`Working with Hosted Zones`: http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/AboutHZWorkingWith.html



======
Output
======

HostedZone -> (structure)

  

  A complex type that contains general information about the hosted zone.

  

  Id -> (string)

    

    The ID that Amazon Route 53 assigned to the hosted zone when you created it.

    

    

  Name -> (string)

    

    The name of the domain. For public hosted zones, this is the name that you have registered with your DNS registrar.

     

    For information about how to specify characters other than ``a-z`` , ``0-9`` , and ``-`` (hyphen) and how to specify internationalized domain names, see  create-hosted-zone .

    

    

  CallerReference -> (string)

    

    The value that you specified for ``CallerReference`` when you created the hosted zone.

    

    

  Config -> (structure)

    

    A complex type that includes the ``Comment`` and ``PrivateZone`` elements. If you omitted the ``hosted-zone-config`` and ``Comment`` elements from the request, the ``Config`` and ``Comment`` elements don't appear in the response.

    

    Comment -> (string)

      

      Any comments that you want to include about the hosted zone.

      

      

    PrivateZone -> (boolean)

      

      A value that indicates whether this is a private hosted zone.

      

      

    

  ResourceRecordSetCount -> (long)

    

    The number of resource record sets in the hosted zone.

    

    

  

ChangeInfo -> (structure)

  

  A complex type that contains information about the ``create-hosted-zone`` request.

  

  Id -> (string)

    

    The ID of the request.

    

    

  Status -> (string)

    

    The current state of the request. ``PENDING`` indicates that this request has not yet been applied to all Amazon Route 53 DNS servers.

    

    

  SubmittedAt -> (timestamp)

    

    The date and time that the change request was submitted in `ISO 8601 format <https://en.wikipedia.org/wiki/ISO_8601>`_ and Coordinated Universal Time (UTC). For example, the value ``2017-03-27T17:48:16.751Z`` represents March 27, 2017 at 17:48:16.751 UTC.

    

    

  Comment -> (string)

    

    A complex type that describes change information about changes made to your hosted zone.

     

    This element contains an ID that you use when performing a  get-change action to get detailed information about the change.

    

    

  

DelegationSet -> (structure)

  

  A complex type that describes the name servers for this hosted zone.

  

  Id -> (string)

    

    The ID that Amazon Route 53 assigns to a reusable delegation set.

    

    

  CallerReference -> (string)

    

    The value that you specified for ``CallerReference`` when you created the reusable delegation set.

    

    

  NameServers -> (list)

    

    A complex type that contains a list of the authoritative name servers for a hosted zone or for a reusable delegation set.

    

    (string)

      

      

    

  

VPC -> (structure)

  

  A complex type that contains information about an Amazon vpc that you associated with this hosted zone.

  

  VPCRegion -> (string)

    

    (Private hosted zones only) The region in which you created an Amazon VPC.

    

    

  VPCId -> (string)

    

    (Private hosted zones only) The ID of an Amazon VPC. 

    

    

  

Location -> (string)

  

  The unique URL representing the new hosted zone.

  

  

