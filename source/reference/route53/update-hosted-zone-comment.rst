[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 update-hosted-zone-comment:


**************************
update-hosted-zone-comment
**************************



===========
Description
===========



To update the hosted zone comment, send a ``POST`` request to the ``/*Route 53 API version* /hostedzone/*hosted zone ID*`` resource. The request body must include a document with a ``UpdateHostedZoneCommentRequest`` element. The response to this request includes the modified ``HostedZone`` element.

 

.. note::

  The comment can have a maximum length of 256 characters.



========
Synopsis
========

::

    update-hosted-zone-comment
  --id <value>
  [--comment <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--id`` (string)


  The ID of the hosted zone you want to update.

  

``--comment`` (string)


  A comment about your hosted zone.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

HostedZone -> (structure)

  

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

    

    

  

