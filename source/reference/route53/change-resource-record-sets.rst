[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 change-resource-record-sets:


***************************
change-resource-record-sets
***************************



===========
Description
===========



Use this action to create or change your authoritative DNS information. To use this action, send a ``POST`` request to the ``/*Route 53 API version* /hostedzone/*hosted Zone ID* /rrset`` resource. The request body must include a document with a ``ChangeResourceRecordSetsRequest`` element.

 

Changes are a list of change items and are considered transactional. For more information on transactional changes, also known as change batches, see `POST change-resource-record-sets`_ in the *Amazon Route 53 API Reference* .

 

.. warning::

  Due to the nature of transactional changes, you cannot delete the same resource record set more than once in a single change batch. If you attempt to delete the same change batch more than once, Amazon Route 53 returns an ``InvalidChangeBatch`` error.

 

In response to a ``change-resource-record-sets`` request, your DNS data is changed on all Amazon Route 53 DNS servers. Initially, the status of a change is ``PENDING`` . This means the change has not yet propagated to all the authoritative Amazon Route 53 DNS servers. When the change is propagated to all hosts, the change returns a status of ``INSYNC`` .

 

Note the following limitations on a ``change-resource-record-sets`` request:

 

 
* A request cannot contain more than 100 Change elements.
 
* A request cannot contain more than 1000 ResourceRecord elements.
 
* The sum of the number of characters (including spaces) in all ``Value`` elements in a request cannot exceed 32,000 characters.
 



========
Synopsis
========

::

    change-resource-record-sets
  --hosted-zone-id <value>
  --change-batch <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




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
          "Type": "SOA"|"A"|"TXT"|"NS"|"CNAME"|"MX"|"PTR"|"SRV"|"SPF"|"AAAA",
          "SetIdentifier": "string",
          "Weight": long,
          "Region": "us-east-1"|"us-west-1"|"us-west-2"|"eu-west-1"|"eu-central-1"|"ap-southeast-1"|"ap-southeast-2"|"ap-northeast-1"|"ap-northeast-2"|"sa-east-1"|"cn-north-1",
          "GeoLocation": {
            "ContinentCode": "string",
            "CountryCode": "string",
            "SubdivisionCode": "string"
          },
          "Failover": "PRIMARY"|"SECONDARY",
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

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

    

    The ID of the request. Use this ID to track when the change has completed across all Amazon Route 53 DNS servers.

    

    

  Status -> (string)

    

    The current state of the request. ``PENDING`` indicates that this request has not yet been applied to all Amazon Route 53 DNS servers.

     

    Valid Values: ``PENDING`` | ``INSYNC`` 

    

    

  SubmittedAt -> (timestamp)

    

    The date and time the change was submitted, in the format ``YYYY-MM-DDThh:mm:ssZ`` , as specified in the ISO 8601 standard (for example, 2009-11-19T19:37:58Z). The ``Z`` after the time indicates that the time is listed in Coordinated Universal Time (UTC).

    

    

  Comment -> (string)

    

    A complex type that describes change information about changes made to your hosted zone.

     

    This element contains an ID that you use when performing a  get-change action to get detailed information about the change.

    

    

  



.. _POST change-resource-record-sets: http://docs.aws.amazon.com/Route53/latest/APIReference/API_ChangeResourceRecordSets.html
