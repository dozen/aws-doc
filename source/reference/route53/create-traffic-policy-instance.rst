[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 create-traffic-policy-instance:


******************************
create-traffic-policy-instance
******************************



===========
Description
===========



Creates resource record sets in a specified hosted zone based on the settings in a specified traffic policy version. In addition, ``create-traffic-policy-instance`` associates the resource record sets with a specified domain name (such as example.com) or subdomain name (such as www.example.com). Amazon Route 53 responds to DNS queries for the domain or subdomain name by using the resource record sets that ``create-traffic-policy-instance`` created.

 

To create a traffic policy instance, send a ``POST`` request to the ``/*Route 53 API version* /trafficpolicyinstance`` resource. The request body must include a document with a ``CreateTrafficPolicyRequest`` element. The response returns the ``CreateTrafficPolicyInstanceResponse`` element, which contains information about the traffic policy instance.



========
Synopsis
========

::

    create-traffic-policy-instance
  --hosted-zone-id <value>
  --name <value>
  --ttl <value>
  --traffic-policy-id <value>
  --traffic-policy-version <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--hosted-zone-id`` (string)


  The ID of the hosted zone in which you want Amazon Route 53 to create resource record sets by using the configuration in a traffic policy.

  

``--name`` (string)


  The domain name (such as example.com) or subdomain name (such as www.example.com) for which Amazon Route 53 responds to DNS queries by using the resource record sets that Amazon Route 53 creates for this traffic policy instance.

  

``--ttl`` (long)


  The ttl that you want Amazon Route 53 to assign to all of the resource record sets that it creates in the specified hosted zone.

  

``--traffic-policy-id`` (string)


  The ID of the traffic policy that you want to use to create resource record sets in the specified hosted zone.

  

``--traffic-policy-version`` (integer)


  The version of the traffic policy that you want to use to create resource record sets in the specified hosted zone.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

TrafficPolicyInstance -> (structure)

  

  A complex type that contains settings for the new traffic policy instance.

  

  Id -> (string)

    

    

  HostedZoneId -> (string)

    

    

  Name -> (string)

    

    

  TTL -> (long)

    

    

  State -> (string)

    

    

  Message -> (string)

    

    

  TrafficPolicyId -> (string)

    

    

  TrafficPolicyVersion -> (integer)

    

    

  TrafficPolicyType -> (string)

    

    

  

Location -> (string)

  

  A unique URL that represents a new traffic policy instance.

  

  

