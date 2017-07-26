[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 get-hosted-zone:


***************
get-hosted-zone
***************



===========
Description
===========



Gets information about a specified hosted zone including the four name servers assigned to the hosted zone.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53-2013-04-01/GetHostedZone>`_


========
Synopsis
========

::

    get-hosted-zone
  --id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--id`` (string)


  The ID of the hosted zone that you want to get information about.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get information about a hosted zone**

The following ``get-hosted-zone`` command gets information about the hosted zone with an ``id`` of ``Z1R8UBAEXAMPLE``::

  aws route53 get-hosted-zone --id Z1R8UBAEXAMPLE


======
Output
======

HostedZone -> (structure)

  

  A complex type that contains general information about the specified hosted zone.

  

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

    

    

  

DelegationSet -> (structure)

  

  A complex type that lists the Amazon Route 53 name servers for the specified hosted zone.

  

  Id -> (string)

    

    The ID that Amazon Route 53 assigns to a reusable delegation set.

    

    

  CallerReference -> (string)

    

    The value that you specified for ``CallerReference`` when you created the reusable delegation set.

    

    

  NameServers -> (list)

    

    A complex type that contains a list of the authoritative name servers for a hosted zone or for a reusable delegation set.

    

    (string)

      

      

    

  

VPCs -> (list)

  

  A complex type that contains information about the VPCs that are associated with the specified hosted zone.

  

  (structure)

    

    (Private hosted zones only) A complex type that contains information about an Amazon VPC.

    

    VPCRegion -> (string)

      

      (Private hosted zones only) The region in which you created an Amazon VPC.

      

      

    VPCId -> (string)

      

      (Private hosted zones only) The ID of an Amazon VPC. 

      

      

    

  

