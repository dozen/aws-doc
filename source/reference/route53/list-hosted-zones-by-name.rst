[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 list-hosted-zones-by-name:


*************************
list-hosted-zones-by-name
*************************



===========
Description
===========



Retrieves a list of your hosted zones in lexicographic order. The response includes a ``HostedZones`` child element for each hosted zone created by the current AWS account. 

 

 ``list-hosted-zones-by-name`` sorts hosted zones by name with the labels reversed. For example:

 

 ``com.example.www.``  

 

Note the trailing dot, which can change the sort order in some circumstances.

 

If the domain name includes escape characters or Punycode, ``list-hosted-zones-by-name`` alphabetizes the domain name using the escaped or Punycoded value, which is the format that Amazon Route 53 saves in its database. For example, to create a hosted zone for exämple.com, you specify ex\344mple.com for the domain name. ``list-hosted-zones-by-name`` alphabetizes it as:

 

 ``com.ex\344mple.``  

 

The labels are reversed and alphabetized using the escaped value. For more information about valid domain name formats, including internationalized domain names, see `DNS Domain Name Format <http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/DomainNameFormat.html>`_ in the *Amazon Route 53 Developer Guide* .

 

Amazon Route 53 returns up to 100 items in each response. If you have a lot of hosted zones, use the ``MaxItems`` parameter to list them in groups of up to 100. The response includes values that help navigate from one group of ``MaxItems`` hosted zones to the next:

 

 
* The ``dns-name`` and ``HostedZoneId`` elements in the response contain the values, if any, specified for the ``dnsname`` and ``hostedzoneid`` parameters in the request that produced the current response. 
 
* The ``MaxItems`` element in the response contains the value, if any, that you specified for the ``maxitems`` parameter in the request that produced the current response. 
 
* If the value of ``IsTruncated`` in the response is true, there are more hosted zones associated with the current AWS account.  If ``IsTruncated`` is false, this response includes the last hosted zone that is associated with the current account. The ``NextDNSName`` element and ``NextHostedZoneId`` elements are omitted from the response. 
 
* The ``NextDNSName`` and ``NextHostedZoneId`` elements in the response contain the domain name and the hosted zone ID of the next hosted zone that is associated with the current AWS account. If you want to list more hosted zones, make another call to ``list-hosted-zones-by-name`` , and specify the value of ``NextDNSName`` and ``NextHostedZoneId`` in the ``dnsname`` and ``hostedzoneid`` parameters, respectively. 
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53-2013-04-01/ListHostedZonesByName>`_


========
Synopsis
========

::

    list-hosted-zones-by-name
  [--dns-name <value>]
  [--hosted-zone-id <value>]
  [--max-items <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dns-name`` (string)


  (Optional) For your first request to ``list-hosted-zones-by-name`` , include the ``dnsname`` parameter only if you want to specify the name of the first hosted zone in the response. If you don't include the ``dnsname`` parameter, Amazon Route 53 returns all of the hosted zones that were created by the current AWS account, in ASCII order. For subsequent requests, include both ``dnsname`` and ``hostedzoneid`` parameters. For ``dnsname`` , specify the value of ``NextDNSName`` from the previous response.

  

``--hosted-zone-id`` (string)


  (Optional) For your first request to ``list-hosted-zones-by-name`` , do not include the ``hostedzoneid`` parameter.

   

  If you have more hosted zones than the value of ``maxitems`` , ``list-hosted-zones-by-name`` returns only the first ``maxitems`` hosted zones. To get the next group of ``maxitems`` hosted zones, submit another request to ``list-hosted-zones-by-name`` and include both ``dnsname`` and ``hostedzoneid`` parameters. For the value of ``hostedzoneid`` , specify the value of the ``NextHostedZoneId`` element from the previous response.

  

``--max-items`` (string)


  The maximum number of hosted zones to be included in the response body for this request. If you have more than ``maxitems`` hosted zones, then the value of the ``IsTruncated`` element in the response is true, and the values of ``NextDNSName`` and ``NextHostedZoneId`` specify the first hosted zone in the next group of ``maxitems`` hosted zones. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

  

  A complex type that contains general information about the hosted zone.

  

  (structure)

    

    A complex type that contains general information about the hosted zone.

    

    Id -> (string)

      

      The ID that Amazon Route 53 assigned to the hosted zone when you created it.

      

      

    Name -> (string)

      

      The name of the domain. For public hosted zones, this is the name that you have registered with your DNS registrar.

       

      For information about how to specify characters other than ``a-z`` , ``0-9`` , and ``-`` (hyphen) and how to specify internationalized domain names, see  create-hosted-zone .

      

      

    CallerReference -> (string)

      

      The value that you specified for ``CallerReference`` when you created the hosted zone.

      

      

    Config -> (structure)

      

      A complex type that includes the ``Comment`` and ``PrivateZone`` elements. If you omitted the ``HostedZoneConfig`` and ``Comment`` elements from the request, the ``Config`` and ``Comment`` elements don't appear in the response.

      

      Comment -> (string)

        

        Any comments that you want to include about the hosted zone.

        

        

      PrivateZone -> (boolean)

        

        A value that indicates whether this is a private hosted zone.

        

        

      

    ResourceRecordSetCount -> (long)

      

      The number of resource record sets in the hosted zone.

      

      

    

  

DNSName -> (string)

  

  For the second and subsequent calls to ``list-hosted-zones-by-name`` , ``dns-name`` is the value that you specified for the ``dnsname`` parameter in the request that produced the current response.

  

  

HostedZoneId -> (string)

  

  The ID that Amazon Route 53 assigned to the hosted zone when you created it.

  

  

IsTruncated -> (boolean)

  

  A flag that indicates whether there are more hosted zones to be listed. If the response was truncated, you can get the next group of ``maxitems`` hosted zones by calling ``list-hosted-zones-by-name`` again and specifying the values of ``NextDNSName`` and ``NextHostedZoneId`` elements in the ``dnsname`` and ``hostedzoneid`` parameters.

  

  

NextDNSName -> (string)

  

  If ``IsTruncated`` is true, the value of ``NextDNSName`` is the name of the first hosted zone in the next group of ``maxitems`` hosted zones. Call ``list-hosted-zones-by-name`` again and specify the value of ``NextDNSName`` and ``NextHostedZoneId`` in the ``dnsname`` and ``hostedzoneid`` parameters, respectively.

   

  This element is present only if ``IsTruncated`` is ``true`` .

  

  

NextHostedZoneId -> (string)

  

  If ``IsTruncated`` is ``true`` , the value of ``NextHostedZoneId`` identifies the first hosted zone in the next group of ``maxitems`` hosted zones. Call ``list-hosted-zones-by-name`` again and specify the value of ``NextDNSName`` and ``NextHostedZoneId`` in the ``dnsname`` and ``hostedzoneid`` parameters, respectively.

   

  This element is present only if ``IsTruncated`` is ``true`` .

  

  

MaxItems -> (string)

  

  The value that you specified for the ``maxitems`` parameter in the call to ``list-hosted-zones-by-name`` that produced the current response.

  

  

