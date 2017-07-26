[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 change-resource-record-sets:


***************************
change-resource-record-sets
***************************



===========
Description
===========



Creates, changes, or deletes a resource record set, which contains authoritative DNS information for a specified domain name or subdomain name. For example, you can use ``change-resource-record-sets`` to create a resource record set that routes traffic for test.example.com to a web server that has an IP address of 192.0.2.44.

 

 **Change Batches and Transactional Changes**  

 

The request body must include a document with a ``ChangeResourceRecordSetsRequest`` element. The request body contains a list of change items, known as a change batch. Change batches are considered transactional changes. When using the Amazon Route 53 API to change resource record sets, Amazon Route 53 either makes all or none of the changes in a change batch request. This ensures that Amazon Route 53 never partially implements the intended changes to the resource record sets in a hosted zone. 

 

For example, a change batch request that deletes the ``CNAME`` record for www.example.com and creates an alias resource record set for www.example.com. Amazon Route 53 deletes the first resource record set and creates the second resource record set in a single operation. If either the ``DELETE`` or the ``CREATE`` action fails, then both changes (plus any other changes in the batch) fail, and the original ``CNAME`` record continues to exist.

 

.. warning::

   

  Due to the nature of transactional changes, you can't delete the same resource record set more than once in a single change batch. If you attempt to delete the same change batch more than once, Amazon Route 53 returns an ``InvalidChangeBatch`` error.

   

 

 **Traffic Flow**  

 

To create resource record sets for complex routing configurations, use either the traffic flow visual editor in the Amazon Route 53 console or the API actions for traffic policies and traffic policy instances. Save the configuration as a traffic policy, then associate the traffic policy with one or more domain names (such as example.com) or subdomain names (such as www.example.com), in the same hosted zone or in multiple hosted zones. You can roll back the updates if the new configuration isn't performing as expected. For more information, see `Using Traffic Flow to Route DNS Traffic <http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/traffic-flow.html>`_ in the *Amazon Route 53 Developer Guide* .

 

 **Create, Delete, and Upsert**  

 

Use ``ChangeResourceRecordsSetsRequest`` to perform the following actions:

 

 
* ``CREATE`` : Creates a resource record set that has the specified values. 
 
* ``DELETE`` : Deletes an existing resource record set that has the specified values. 
 
* ``UPSERT`` : If a resource record set does not already exist, AWS creates it. If a resource set does exist, Amazon Route 53 updates it with the values in the request.  
 

 

 **Syntaxes for Creating, Updating, and Deleting Resource Record Sets**  

 

The syntax for a request depends on the type of resource record set that you want to create, delete, or update, such as weighted, alias, or failover. The XML elements in your request must appear in the order listed in the syntax. 

 

For an example for each type of resource record set, see "Examples."

 

Don't refer to the syntax in the "Parameter Syntax" section, which includes all of the elements for every kind of resource record set that you can create, delete, or update by using ``change-resource-record-sets`` . 

 

 **Change Propagation to Amazon Route 53 DNS Servers**  

 

When you submit a ``change-resource-record-sets`` request, Amazon Route 53 propagates your changes to all of the Amazon Route 53 authoritative DNS servers. While your changes are propagating, ``get-change`` returns a status of ``PENDING`` . When propagation is complete, ``get-change`` returns a status of ``INSYNC`` . Changes generally propagate to all Amazon Route 53 name servers within 60 seconds. For more information, see  get-change .

 

 **Limits on change-resource-record-sets Requests**  

 

For information about the limits on a ``change-resource-record-sets`` request, see `Limits <http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/DNSLimitations.html>`_ in the *Amazon Route 53 Developer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53-2013-04-01/ChangeResourceRecordSets>`_


========
Synopsis
========

::

    change-resource-record-sets
  --hosted-zone-id <value>
  --change-batch <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--hosted-zone-id`` (string)


  The ID of the hosted zone that contains the resource record sets that you want to change.

  

``--change-batch`` (structure)


  A complex type that contains an optional comment and the ``Changes`` element.

  



JSON Syntax::

  {
    "Comment": "string",
    "Changes": [
      {
        "Action": "CREATE"|"DELETE"|"UPSERT",
        "ResourceRecordSet": {
          "Name": "string",
          "Type": "SOA"|"A"|"TXT"|"NS"|"CNAME"|"MX"|"NAPTR"|"PTR"|"SRV"|"SPF"|"AAAA",
          "SetIdentifier": "string",
          "Weight": long,
          "Region": "us-east-1"|"us-east-2"|"us-west-1"|"us-west-2"|"ca-central-1"|"eu-west-1"|"eu-west-2"|"eu-central-1"|"ap-southeast-1"|"ap-southeast-2"|"ap-northeast-1"|"ap-northeast-2"|"sa-east-1"|"cn-north-1"|"ap-south-1",
          "GeoLocation": {
            "ContinentCode": "string",
            "CountryCode": "string",
            "SubdivisionCode": "string"
          },
          "Failover": "PRIMARY"|"SECONDARY",
          "MultiValueAnswer": true|false,
          "TTL": long,
          "ResourceRecords": [
            {
              "Value": "string"
            }
            ...
          ],
          "AliasTarget": {
            "HostedZoneId": "string",
            "DNSName": "string",
            "EvaluateTargetHealth": true|false
          },
          "HealthCheckId": "string",
          "TrafficPolicyInstanceId": "string"
        }
      }
      ...
    ]
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create, update, or delete a resource record set**

The following ``change-resource-record-sets`` command creates a resource record set using the ``hosted-zone-id`` ``Z1R8UBAEXAMPLE`` and the JSON-formatted configuration in the file ``C:\awscli\route53\change-resource-record-sets.json``::

  aws route53 change-resource-record-sets --hosted-zone-id Z1R8UBAEXAMPLE --change-batch file://C:\awscli\route53\change-resource-record-sets.json

For more information, see `POST ChangeResourceRecordSets`_ in the *Amazon Route 53 API Reference*.

.. _`POST ChangeResourceRecordSets`: http://docs.aws.amazon.com/Route53/latest/APIReference/API_ChangeResourceRecordSets.html


The configuration in the JSON file depends on the kind of resource record set you want to create:

- Basic

- Weighted

- Alias

- Weighted Alias

- Latency

- Latency Alias

- Failover

- Failover Alias



**Basic Syntax**::

  {
    "Comment": "optional comment about the changes in this change batch request",
    "Changes": [
      {
        "Action": "CREATE"|"DELETE"|"UPSERT",
        "ResourceRecordSet": {
          "Name": "DNS domain name",
          "Type": "SOA"|"A"|"TXT"|"NS"|"CNAME"|"MX"|"PTR"|"SRV"|"SPF"|"AAAA",
          "TTL": time to live in seconds,
          "ResourceRecords": [
            {
              "Value": "applicable value for the record type"
            },
            {...}
          ]
        }
      },
      {...}
    ]
  }


**Weighted Syntax**::

  {
    "Comment": "optional comment about the changes in this change batch request",
    "Changes": [
      {
        "Action": "CREATE"|"DELETE"|"UPSERT",
        "ResourceRecordSet": {
          "Name": "DNS domain name",
          "Type": "SOA"|"A"|"TXT"|"NS"|"CNAME"|"MX"|"PTR"|"SRV"|"SPF"|"AAAA",
          "SetIdentifier": "unique description for this resource record set",
          "Weight": value between 0 and 255,
          "TTL": time to live in seconds,
          "ResourceRecords": [
            {
              "Value": "applicable value for the record type"
            },
            {...}
          ],
          "HealthCheckId": "optional ID of an Amazon Route 53 health check"
        }
      },
      {...}
    ]
  }


**Alias Syntax**::

  {
    "Comment": "optional comment about the changes in this change batch request",
    "Changes": [
      {
        "Action": "CREATE"|"DELETE"|"UPSERT",
        "ResourceRecordSet": {
          "Name": "DNS domain name",
          "Type": "SOA"|"A"|"TXT"|"NS"|"CNAME"|"MX"|"PTR"|"SRV"|"SPF"|"AAAA",
          "AliasTarget": {
            "HostedZoneId": "hosted zone ID for your CloudFront distribution, Amazon S3 bucket, Elastic Load Balancing load balancer, or Amazon Route 53 hosted zone",
            "DNSName": "DNS domain name for your CloudFront distribution, Amazon S3 bucket, Elastic Load Balancing load balancer, or another resource record set in this hosted zone",
            "EvaluateTargetHealth": true|false
          },
          "HealthCheckId": "optional ID of an Amazon Route 53 health check"
        }
      },
      {...}
    ]
  }


**Weighted Alias Syntax**::

  {
    "Comment": "optional comment about the changes in this change batch request",
    "Changes": [
      {
        "Action": "CREATE"|"DELETE"|"UPSERT",
        "ResourceRecordSet": {
          "Name": "DNS domain name",
          "Type": "SOA"|"A"|"TXT"|"NS"|"CNAME"|"MX"|"PTR"|"SRV"|"SPF"|"AAAA",
          "SetIdentifier": "unique description for this resource record set",
          "Weight": value between 0 and 255,
          "AliasTarget": {
            "HostedZoneId": "hosted zone ID for your CloudFront distribution, Amazon S3 bucket, Elastic Load Balancing load balancer, or Amazon Route 53 hosted zone",
            "DNSName": "DNS domain name for your CloudFront distribution, Amazon S3 bucket, Elastic Load Balancing load balancer, or another resource record set in this hosted zone",
            "EvaluateTargetHealth": true|false
          },
          "HealthCheckId": "optional ID of an Amazon Route 53 health check"
        }
      },
      {...}
    ]
  }



**Latency Syntax**::

  {
    "Comment": "optional comment about the changes in this change batch request",
    "Changes": [
      {
        "Action": "CREATE"|"DELETE"|"UPSERT",
        "ResourceRecordSet": {
          "Name": "DNS domain name",
          "Type": "SOA"|"A"|"TXT"|"NS"|"CNAME"|"MX"|"PTR"|"SRV"|"SPF"|"AAAA",
          "SetIdentifier": "unique description for this resource record set",
          "Region": "Amazon EC2 region name",
          "TTL": time to live in seconds,
          "ResourceRecords": [
            {
              "Value": "applicable value for the record type"
            },
            {...}
          ],
          "HealthCheckId": "optional ID of an Amazon Route 53 health check"
        }
      },
      {...}
    ]
  }


**Latency Alias Syntax**::

  {
    "Comment": "optional comment about the changes in this change batch request",
    "Changes": [
      {
        "Action": "CREATE"|"DELETE"|"UPSERT",
        "ResourceRecordSet": {
          "Name": "DNS domain name",
          "Type": "SOA"|"A"|"TXT"|"NS"|"CNAME"|"MX"|"PTR"|"SRV"|"SPF"|"AAAA",
          "SetIdentifier": "unique description for this resource record set",
          "Region": "Amazon EC2 region name",
          "AliasTarget": {
            "HostedZoneId": "hosted zone ID for your CloudFront distribution, Amazon S3 bucket, Elastic Load Balancing load balancer, or Amazon Route 53 hosted zone",
            "DNSName": "DNS domain name for your CloudFront distribution, Amazon S3 bucket, Elastic Load Balancing load balancer, or another resource record set in this hosted zone",
            "EvaluateTargetHealth": true|false
          },
          "HealthCheckId": "optional ID of an Amazon Route 53 health check"
        }
      },
      {...}
    ]
  }


**Failover Syntax**::

  {
    "Comment": "optional comment about the changes in this change batch request",
    "Changes": [
      {
        "Action": "CREATE"|"DELETE"|"UPSERT",
        "ResourceRecordSet": {
          "Name": "DNS domain name",
          "Type": "SOA"|"A"|"TXT"|"NS"|"CNAME"|"MX"|"PTR"|"SRV"|"SPF"|"AAAA",
          "SetIdentifier": "unique description for this resource record set",
          "Failover": "PRIMARY" | "SECONDARY",
          "TTL": time to live in seconds,
          "ResourceRecords": [
            {
              "Value": "applicable value for the record type"
            },
            {...}
          ],
          "HealthCheckId": "ID of an Amazon Route 53 health check"
        }
      },
      {...}
    ]
  }


**Failover Alias Syntax**::

  {
    "Comment": "optional comment about the changes in this change batch request",
    "Changes": [
      {
        "Action": "CREATE"|"DELETE"|"UPSERT",
        "ResourceRecordSet": {
          "Name": "DNS domain name",
          "Type": "SOA"|"A"|"TXT"|"NS"|"CNAME"|"MX"|"PTR"|"SRV"|"SPF"|"AAAA",
          "SetIdentifier": "unique description for this resource record set",
          "Failover": "PRIMARY" | "SECONDARY",
          "AliasTarget": {
            "HostedZoneId": "hosted zone ID for your CloudFront distribution, Amazon S3 bucket, Elastic Load Balancing load balancer, or Amazon Route 53 hosted zone",
            "DNSName": "DNS domain name for your CloudFront distribution, Amazon S3 bucket, Elastic Load Balancing load balancer, or another resource record set in this hosted zone",
            "EvaluateTargetHealth": true|false
          },
          "HealthCheckId": "optional ID of an Amazon Route 53 health check"
        }
      },
      {...}
    ]
  }


======
Output
======

ChangeInfo -> (structure)

  

  A complex type that contains information about changes made to your hosted zone.

   

  This element contains an ID that you use when performing a  get-change action to get detailed information about the change.

  

  Id -> (string)

    

    The ID of the request.

    

    

  Status -> (string)

    

    The current state of the request. ``PENDING`` indicates that this request has not yet been applied to all Amazon Route 53 DNS servers.

    

    

  SubmittedAt -> (timestamp)

    

    The date and time that the change request was submitted in `ISO 8601 format <https://en.wikipedia.org/wiki/ISO_8601>`_ and Coordinated Universal Time (UTC). For example, the value ``2017-03-27T17:48:16.751Z`` represents March 27, 2017 at 17:48:16.751 UTC.

    

    

  Comment -> (string)

    

    A complex type that describes change information about changes made to your hosted zone.

     

    This element contains an ID that you use when performing a  get-change action to get detailed information about the change.

    

    

  

