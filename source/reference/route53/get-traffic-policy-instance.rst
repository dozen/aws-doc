[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 get-traffic-policy-instance:


***************************
get-traffic-policy-instance
***************************



===========
Description
===========



Gets information about a specified traffic policy instance.

 

To get information about the traffic policy instance, send a ``GET`` request to the ``/*Route 53 API version* /trafficpolicyinstance`` resource.

 

.. note::

  After you submit a ``create-traffic-policy-instance`` or an ``update-traffic-policy-instance`` request, there's a brief delay while Amazon Route 53 creates the resource record sets that are specified in the traffic policy definition. For more information, see the  State response element. 



========
Synopsis
========

::

    get-traffic-policy-instance
  --id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--id`` (string)


  The ID of the traffic policy instance that you want to get information about.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

TrafficPolicyInstance -> (structure)

  

  A complex type that contains settings for the traffic policy instance.

  

  Id -> (string)

    

    

  HostedZoneId -> (string)

    

    

  Name -> (string)

    

    

  TTL -> (long)

    

    

  State -> (string)

    

    

  Message -> (string)

    

    

  TrafficPolicyId -> (string)

    

    

  TrafficPolicyVersion -> (integer)

    

    

  TrafficPolicyType -> (string)

    

    

  

