[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 disassociate-vpc-from-hosted-zone:


*********************************
disassociate-vpc-from-hosted-zone
*********************************



===========
Description
===========



Disassociates a vpc from a Amazon Route 53 private hosted zone. 

 

.. note::

   

  You can't disassociate the last vpc from a private hosted zone.

   

 

.. warning::

   

  You can't disassociate a vpc from a private hosted zone when only one vpc is associated with the hosted zone. You also can't convert a private hosted zone into a public hosted zone.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53-2013-04-01/DisassociateVPCFromHostedZone>`_


========
Synopsis
========

::

    disassociate-vpc-from-hosted-zone
  --hosted-zone-id <value>
  --vpc <value>
  [--comment <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--hosted-zone-id`` (string)


  The ID of the private hosted zone that you want to disassociate a vpc from.

  

``--vpc`` (structure)


  A complex type that contains information about the vpc that you're disassociating from the specified hosted zone.

  



Shorthand Syntax::

    VPCRegion=string,VPCId=string




JSON Syntax::

  {
    "VPCRegion": "us-east-1"|"us-east-2"|"us-west-1"|"us-west-2"|"eu-west-1"|"eu-west-2"|"eu-central-1"|"ap-southeast-1"|"ap-southeast-2"|"ap-south-1"|"ap-northeast-1"|"ap-northeast-2"|"sa-east-1"|"ca-central-1"|"cn-north-1",
    "VPCId": "string"
  }



``--comment`` (string)


   *Optional:* A comment about the disassociation request.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

ChangeInfo -> (structure)

  

  A complex type that describes the changes made to the specified private hosted zone.

  

  Id -> (string)

    

    The ID of the request.

    

    

  Status -> (string)

    

    The current state of the request. ``PENDING`` indicates that this request has not yet been applied to all Amazon Route 53 DNS servers.

    

    

  SubmittedAt -> (timestamp)

    

    The date and time that the change request was submitted in `ISO 8601 format <https://en.wikipedia.org/wiki/ISO_8601>`_ and Coordinated Universal Time (UTC). For example, the value ``2017-03-27T17:48:16.751Z`` represents March 27, 2017 at 17:48:16.751 UTC.

    

    

  Comment -> (string)

    

    A complex type that describes change information about changes made to your hosted zone.

     

    This element contains an ID that you use when performing a  get-change action to get detailed information about the change.

    

    

  

