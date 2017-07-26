[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 create-reusable-delegation-set:


******************************
create-reusable-delegation-set
******************************



===========
Description
===========



This action creates a reusable delegationSet.

 

To create a new reusable delegationSet, send a ``POST`` request to the ``/*Route 53 API version* /delegationset`` resource. The request body must include a document with a ``CreateReusableDelegationSetRequest`` element. The response returns the ``CreateReusableDelegationSetResponse`` element that contains metadata about the delegationSet. 

 

If the optional parameter HostedZoneId is specified, it marks the delegationSet associated with that particular hosted zone as reusable. 



========
Synopsis
========

::

    create-reusable-delegation-set
  --caller-reference <value>
  [--hosted-zone-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--caller-reference`` (string)


  A unique string that identifies the request and that allows failed ``create-reusable-delegation-set`` requests to be retried without the risk of executing the operation twice. You must use a unique ``CallerReference`` string every time you create a reusable delegation set. ``CallerReference`` can be any unique string; you might choose to use a string that identifies your project, such as ``DNSMigration_01`` .

   

  Valid characters are any Unicode code points that are legal in an XML 1.0 document. The UTF-8 encoding of the value must be less than 128 bytes.

  

``--hosted-zone-id`` (string)


  The ID of the hosted zone whose delegation set you want to mark as reusable. It is an optional parameter.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

DelegationSet -> (structure)

  

  A complex type that contains name server information.

  

  Id -> (string)

    

    

  CallerReference -> (string)

    

    

  NameServers -> (list)

    

    A complex type that contains the authoritative name servers for the hosted zone. Use the method provided by your domain registrar to add an NS record to your domain for each ``NameServer`` that is assigned to your hosted zone.

    

    (string)

      

      

    

  

Location -> (string)

  

  The unique URL representing the new reusbale delegation set.

  

  

