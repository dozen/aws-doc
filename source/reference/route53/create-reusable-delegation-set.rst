[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 create-reusable-delegation-set:


******************************
create-reusable-delegation-set
******************************



===========
Description
===========



Creates a delegation set (a group of four name servers) that can be reused by multiple hosted zones. If a hosted zoned ID is specified, ``create-reusable-delegation-set`` marks the delegation set associated with that zone as reusable

 

.. note::

   

  A reusable delegation set can't be associated with a private hosted zone.

   

 

For information on how to use a reusable delegation set to configure white label name servers, see `Configuring White Label Name Servers <http://docs.aws.amazon.com/Route53/latest/DeveloperGuide/white-label-name-servers.html>`_ .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53-2013-04-01/CreateReusableDelegationSet>`_


========
Synopsis
========

::

    create-reusable-delegation-set
  --caller-reference <value>
  [--hosted-zone-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--caller-reference`` (string)


  A unique string that identifies the request, and that allows you to retry failed ``create-reusable-delegation-set`` requests without the risk of executing the operation twice. You must use a unique ``CallerReference`` string every time you submit a ``create-reusable-delegation-set`` request. ``CallerReference`` can be any unique string, for example a date/time stamp.

  

``--hosted-zone-id`` (string)


  If you want to mark the delegation set for an existing hosted zone as reusable, the ID for that hosted zone.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DelegationSet -> (structure)

  

  A complex type that contains name server information.

  

  Id -> (string)

    

    The ID that Amazon Route 53 assigns to a reusable delegation set.

    

    

  CallerReference -> (string)

    

    The value that you specified for ``CallerReference`` when you created the reusable delegation set.

    

    

  NameServers -> (list)

    

    A complex type that contains a list of the authoritative name servers for a hosted zone or for a reusable delegation set.

    

    (string)

      

      

    

  

Location -> (string)

  

  The unique URL representing the new reusable delegation set.

  

  

