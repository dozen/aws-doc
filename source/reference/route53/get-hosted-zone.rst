[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 get-hosted-zone:


***************
get-hosted-zone
***************



===========
Description
===========



To retrieve the delegation set for a hosted zone, send a ``GET`` request to the ``/*Route 53 API version* /hostedzone/*hosted zone ID*`` resource. The delegation set is the four Amazon Route 53 name servers that were assigned to the hosted zone when you created it.



========
Synopsis
========

::

    get-hosted-zone
  --id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--id`` (string)


  The ID of the hosted zone for which you want to get a list of the name servers in the delegation set.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

  

  A complex type that contains the information about the specified hosted zone.

  

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

    

    

  

DelegationSet -> (structure)

  

  A complex type that contains information about the name servers for the specified hosted zone.

  

  Id -> (string)

    

    

  CallerReference -> (string)

    

    

  NameServers -> (list)

    

    A complex type that contains the authoritative name servers for the hosted zone. Use the method provided by your domain registrar to add an NS record to your domain for each ``NameServer`` that is assigned to your hosted zone.

    

    (string)

      

      

    

  

VPCs -> (list)

  

  A complex type that contains information about VPCs associated with the specified hosted zone.

  

  (structure)

    

    VPCRegion -> (string)

      

      

    VPCId -> (string)

      

      A VPC ID

      

      

    

  

