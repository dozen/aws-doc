[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 associate-vpc-with-hosted-zone:


******************************
associate-vpc-with-hosted-zone
******************************



===========
Description
===========



This action associates a vpc with an hosted zone. 

 

To associate a vpc with an hosted zone, send a ``POST`` request to the ``/*Route 53 API version* /hostedzone/*hosted zone ID* /associatevpc`` resource. The request body must include a document with a ``AssociateVPCWithHostedZoneRequest`` element. The response returns the ``AssociateVPCWithHostedZoneResponse`` element that contains ``ChangeInfo`` for you to track the progress of the ``AssociateVPCWithHostedZoneRequest`` you made. See ``get-change`` operation for how to track the progress of your change.



========
Synopsis
========

::

    associate-vpc-with-hosted-zone
  --hosted-zone-id <value>
  --vpc <value>
  [--comment <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--hosted-zone-id`` (string)


  The ID of the hosted zone you want to associate your vpc with.

   

  Note that you cannot associate a vpc with a hosted zone that doesn't have an existing vpc association.

  

``--vpc`` (structure)


  The vpc that you want your hosted zone to be associated with. 

  



Shorthand Syntax::

    VPCRegion=string,VPCId=string




JSON Syntax::

  {
    "VPCRegion": "us-east-1"|"us-west-1"|"us-west-2"|"eu-west-1"|"eu-central-1"|"ap-southeast-1"|"ap-southeast-2"|"ap-northeast-1"|"ap-northeast-2"|"sa-east-1"|"cn-north-1",
    "VPCId": "string"
  }



``--comment`` (string)


  *Optional:* Any comments you want to include about a ``AssociateVPCWithHostedZoneRequest`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

ChangeInfo -> (structure)

  

  A complex type that contains the ID, the status, and the date and time of your ``AssociateVPCWithHostedZoneRequest`` .

  

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

    

    

  

