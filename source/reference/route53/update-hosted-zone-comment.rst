[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 update-hosted-zone-comment:


**************************
update-hosted-zone-comment
**************************



===========
Description
===========



Updates the comment for a specified hosted zone.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53-2013-04-01/UpdateHostedZoneComment>`_


========
Synopsis
========

::

    update-hosted-zone-comment
  --id <value>
  [--comment <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--id`` (string)


  The ID for the hosted zone that you want to update the comment for.

  

``--comment`` (string)


  The new comment for the hosted zone. If you don't specify a value for ``Comment`` , Amazon Route 53 deletes the existing value of the ``Comment`` element, if any.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

HostedZone -> (structure)

  

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

    

    

  

