[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 list-hosted-zones-by-name:


*************************
list-hosted-zones-by-name
*************************



===========
Description
===========



To retrieve a list of your hosted zones in lexicographic order, send a ``GET`` request to the ``/*Route 53 API version* /hostedzonesbyname`` resource. The response to this request includes a ``HostedZones`` element with zero or more ``HostedZone`` child elements lexicographically ordered by DNS name. By default, the list of hosted zones is displayed on a single page. You can control the length of the page that is displayed by using the ``MaxItems`` parameter. You can use the ``dns-name`` and ``HostedZoneId`` parameters to control the hosted zone that the list begins with.

 

.. note::

  Amazon Route 53 returns a maximum of 100 items. If you set MaxItems to a value greater than 100, Amazon Route 53 returns only the first 100.



========
Synopsis
========

::

    list-hosted-zones-by-name
  [--dns-name <value>]
  [--hosted-zone-id <value>]
  [--max-items <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--dns-name`` (string)


  The first name in the lexicographic ordering of domain names that you want the ``ListHostedZonesByNameRequest`` request to list.

   

  If the request returned more than one page of results, submit another request and specify the value of ``NextDNSName`` and ``NextHostedZoneId`` from the last response in the ``dns-name`` and ``HostedZoneId`` parameters to get the next page of results.

  

``--hosted-zone-id`` (string)


  If the request returned more than one page of results, submit another request and specify the value of ``NextDNSName`` and ``NextHostedZoneId`` from the last response in the ``dns-name`` and ``HostedZoneId`` parameters to get the next page of results.

  

``--max-items`` (string)


  Specify the maximum number of hosted zones to return per page of results.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

The following command lists up to 100 hosted zones ordered by domain name::

  aws route53 list-hosted-zones-by-name

Output::

  {
    "HostedZones": [
        {
            "ResourceRecordSetCount": 2,
            "CallerReference": "test20150527-2",
            "Config": {
                "Comment": "test2",
                "PrivateZone": false
            },
            "Id": "/hostedzone/Z119WBBTVP5WFX",
            "Name": "2.example.com."
        },
        {
            "ResourceRecordSetCount": 2,
            "CallerReference": "test20150527-1",
            "Config": {
                "Comment": "test",
                "PrivateZone": false
            },
            "Id": "/hostedzone/Z3P5QSUBK4POTI",
            "Name": "www.example.com."
        }
    ],
    "IsTruncated": false,
    "MaxItems": "100"
  }

The following command lists hosted zones ordered by name, beginning with ``www.example.com``::
  
  aws route53 list-hosted-zones-by-name --dns-name www.example.com

Output::

  {
    "HostedZones": [
        {
            "ResourceRecordSetCount": 2,
            "CallerReference": "mwunderl20150527-1",
            "Config": {
                "Comment": "test",
                "PrivateZone": false
            },
            "Id": "/hostedzone/Z3P5QSUBK4POTI",
            "Name": "www.example.com."
        }
    ],
    "DNSName": "www.example.com",
    "IsTruncated": false,
    "MaxItems": "100"
  }

======
Output
======

HostedZones -> (list)

  

  A complex type that contains information about the hosted zones associated with the current AWS account.

  

  (structure)

    

    A complex type that contain information about the specified hosted zone.

    

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

        

        An optional comment about your hosted zone. If you don't want to specify a comment, you can omit the ``HostedZoneConfig`` and ``Comment`` elements from the XML document.

        

        

      PrivateZone -> (boolean)

        

        

      

    ResourceRecordSetCount -> (long)

      

      Total number of resource record sets in the hosted zone.

      

      

    

  

DNSName -> (string)

  

  The ``dns-name`` value sent in the request.

  

  

HostedZoneId -> (string)

  

  The ``HostedZoneId`` value sent in the request.

  

  

IsTruncated -> (boolean)

  

  A flag indicating whether there are more hosted zones to be listed. If your results were truncated, you can make a follow-up request for the next page of results by using the ``NextDNSName`` and ``NextHostedZoneId`` elements.

   

  Valid Values: ``true`` | ``false`` 

  

  

NextDNSName -> (string)

  

  If  ListHostedZonesByNameResponse$IsTruncated is ``true`` , there are more hosted zones associated with the current AWS account. To get the next page of results, make another request to ``list-hosted-zones-by-name`` . Specify the value of  ListHostedZonesByNameResponse$NextDNSName in the  ListHostedZonesByNameRequest$DNSName element and  ListHostedZonesByNameResponse$NextHostedZoneId in the  ListHostedZonesByNameRequest$HostedZoneId element.

  

  

NextHostedZoneId -> (string)

  

  If  ListHostedZonesByNameResponse$IsTruncated is ``true`` , there are more hosted zones associated with the current AWS account. To get the next page of results, make another request to ``list-hosted-zones-by-name`` . Specify the value of  ListHostedZonesByNameResponse$NextDNSName in the  ListHostedZonesByNameRequest$DNSName element and  ListHostedZonesByNameResponse$NextHostedZoneId in the  ListHostedZonesByNameRequest$HostedZoneId element.

  

  

MaxItems -> (string)

  

  The maximum number of hosted zones to be included in the response body. If the number of hosted zones associated with this AWS account exceeds ``MaxItems`` , the value of  ListHostedZonesByNameResponse$IsTruncated in the response is ``true`` . Call ``list-hosted-zones-by-name`` again and specify the value of  ListHostedZonesByNameResponse$NextDNSName and  ListHostedZonesByNameResponse$NextHostedZoneId elements respectively to get the next page of results.

  

  

