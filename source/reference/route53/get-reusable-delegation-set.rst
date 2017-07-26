[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 get-reusable-delegation-set:


***************************
get-reusable-delegation-set
***************************



===========
Description
===========



To retrieve the reusable delegation set, send a ``GET`` request to the ``/*Route 53 API version* /delegationset/*delegation set ID*`` resource.



========
Synopsis
========

::

    get-reusable-delegation-set
  --id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--id`` (string)


  The ID of the reusable delegation set for which you want to get a list of the name server.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

DelegationSet -> (structure)

  

  A complex type that contains the information about the nameservers for the specified delegation set ID.

  

  Id -> (string)

    

    

  CallerReference -> (string)

    

    

  NameServers -> (list)

    

    A complex type that contains the authoritative name servers for the hosted zone. Use the method provided by your domain registrar to add an NS record to your domain for each ``NameServer`` that is assigned to your hosted zone.

    

    (string)

      

      

    

  

