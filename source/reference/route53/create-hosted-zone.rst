[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 create-hosted-zone:


******************
create-hosted-zone
******************



===========
Description
===========



This action creates a new hosted zone.

 

To create a new hosted zone, send a ``POST`` request to the ``/*Route 53 API version* /hostedzone`` resource. The request body must include a document with a ``CreateHostedZoneRequest`` element. The response returns the ``CreateHostedZoneResponse`` element that contains metadata about the hosted zone.

 

Amazon Route 53 automatically creates a default SOA record and four NS records for the zone. The NS records in the hosted zone are the name servers you give your registrar to delegate your domain to. For more information about SOA and NS records, see `NS and SOA Records that Amazon Route 53 Creates for a Hosted Zone`_ in the *Amazon Route 53 Developer Guide* .

 

When you create a zone, its initial status is ``PENDING`` . This means that it is not yet available on all DNS servers. The status of the zone changes to ``INSYNC`` when the NS and SOA records are available on all Amazon Route 53 DNS servers. 

 

When trying to create a hosted zone using a reusable delegation set, you could specify an optional DelegationSetId, and Route53 would assign those 4 NS records for the zone, instead of alloting a new one.



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
  [--generate-cli-skeleton]




=======
Options
=======

``--name`` (string)


  The name of the domain. This must be a fully-specified domain, for example, www.example.com. The trailing dot is optional; Amazon Route 53 assumes that the domain name is fully qualified. This means that Amazon Route 53 treats www.example.com (without a trailing dot) and www.example.com. (with a trailing dot) as identical.

   

  This is the name you have registered with your DNS registrar. You should ask your registrar to change the authoritative name servers for your domain to the set of ``NameServers`` elements returned in ``DelegationSet`` .

  

``--vpc`` (structure)


  The vpc that you want your hosted zone to be associated with. By providing this parameter, your newly created hosted cannot be resolved anywhere other than the given VPC.

  



Shorthand Syntax::

    VPCRegion=string,VPCId=string




JSON Syntax::

  {
    "VPCRegion": "us-east-1"|"us-west-1"|"us-west-2"|"eu-west-1"|"eu-central-1"|"ap-southeast-1"|"ap-southeast-2"|"ap-northeast-1"|"ap-northeast-2"|"sa-east-1"|"cn-north-1",
    "VPCId": "string"
  }



``--caller-reference`` (string)


  A unique string that identifies the request and that allows failed ``create-hosted-zone`` requests to be retried without the risk of executing the operation twice. You must use a unique ``CallerReference`` string every time you create a hosted zone. ``CallerReference`` can be any unique string; you might choose to use a string that identifies your project, such as ``DNSMigration_01`` .

   

  Valid characters are any Unicode code points that are legal in an XML 1.0 document. The UTF-8 encoding of the value must be less than 128 bytes.

  

``--hosted-zone-config`` (structure)


  A complex type that contains an optional comment about your hosted zone.

  



Note do **not** include ``PrivateZone`` in this input structure. Its value is returned in the output to the command.



Shorthand Syntax::

    Comment=string,PrivateZone=boolean




JSON Syntax::

  {
    "Comment": "string",
    "PrivateZone": true|false
  }



``--delegation-set-id`` (string)


  The delegation set id of the reusable delgation set whose NS records you want to assign to the new hosted zone.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

  

  A complex type that contains identifying information about the hosted zone.

  

  Id -> (string)

    

    The ID of the specified hosted zone.

    

    

  Name -> (string)

    

    The name of the domain. This must be a fully-specified domain, for example, www.example.com. The trailing dot is optional; Amazon Route 53 assumes that the domain name is fully qualified. This means that Amazon Route 53 treats www.example.com (without a trailing dot) and www.example.com. (with a trailing dot) as identical.

     

    This is the name you have registered with your DNS registrar. You should ask your registrar to change the authoritative name servers for your domain to the set of ``NameServers`` elements returned in ``DelegationSet`` .

    

    

  CallerReference -> (string)

    

    A unique string that identifies the request to create the hosted zone.

    

    

  Config -> (structure)

    

    A complex type that contains the ``Comment`` element.

    

    Comment -> (string)

      

      An optional comment about your hosted zone. If you don't want to specify a comment, you can omit the ``hosted-zone-config`` and ``Comment`` elements from the XML document.

      

      

    PrivateZone -> (boolean)

      

      

    

  ResourceRecordSetCount -> (long)

    

    Total number of resource record sets in the hosted zone.

    

    

  

ChangeInfo -> (structure)

  

  A complex type that contains information about the request to create a hosted zone. This includes an ID that you use when you call the  get-change action to get the current status of the change request.

  

  Id -> (string)

    

    The ID of the request. Use this ID to track when the change has completed across all Amazon Route 53 DNS servers.

    

    

  Status -> (string)

    

    The current state of the request. ``PENDING`` indicates that this request has not yet been applied to all Amazon Route 53 DNS servers.

     

    Valid Values: ``PENDING`` | ``INSYNC`` 

    

    

  SubmittedAt -> (timestamp)

    

    The date and time the change was submitted, in the format ``YYYY-MM-DDThh:mm:ssZ`` , as specified in the ISO 8601 standard (for example, 2009-11-19T19:37:58Z). The ``Z`` after the time indicates that the time is listed in Coordinated Universal Time (UTC).

    

    

  Comment -> (string)

    

    A complex type that describes change information about changes made to your hosted zone.

     

    This element contains an ID that you use when performing a  get-change action to get detailed information about the change.

    

    

  

DelegationSet -> (structure)

  

  A complex type that contains name server information.

  

  Id -> (string)

    

    

  CallerReference -> (string)

    

    

  NameServers -> (list)

    

    A complex type that contains the authoritative name servers for the hosted zone. Use the method provided by your domain registrar to add an NS record to your domain for each ``NameServer`` that is assigned to your hosted zone.

    

    (string)

      

      

    

  

VPC -> (structure)

  

  VPCRegion -> (string)

    

    

  VPCId -> (string)

    

    A vpc ID

    

    

  

Location -> (string)

  

  The unique URL representing the new hosted zone.

  

  



.. _NS and SOA Records that Amazon Route 53 Creates for a Hosted Zone: http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/SOA-NSrecords.html
