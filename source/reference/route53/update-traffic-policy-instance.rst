[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 update-traffic-policy-instance:


******************************
update-traffic-policy-instance
******************************



===========
Description
===========



Updates the resource record sets in a specified hosted zone that were created based on the settings in a specified traffic policy version.

 

.. warning::

  The DNS type of the resource record sets that you're updating must match the DNS type in the JSON document that is associated with the traffic policy version that you're using to update the traffic policy instance.

 

When you update a traffic policy instance, Amazon Route 53 continues to respond to DNS queries for the root resource record set name (such as example.com) while it replaces one group of resource record sets with another. Amazon Route 53 performs the following operations:

 

 
* Amazon Route 53 creates a new group of resource record sets based on the specified traffic policy. This is true regardless of how substantial the differences are between the existing resource record sets and the new resource record sets. 
 
* When all of the new resource record sets have been created, Amazon Route 53 starts to respond to DNS queries for the root resource record set name (such as example.com) by using the new resource record sets.
 
* Amazon Route 53 deletes the old group of resource record sets that are associated with the root resource record set name.
 

 

To update a traffic policy instance, send a ``POST`` request to the ``/*Route 53 API version* /trafficpolicyinstance/*traffic policy ID*`` resource. The request body must include a document with an ``UpdateTrafficPolicyInstanceRequest`` element.



========
Synopsis
========

::

    update-traffic-policy-instance
  --id <value>
  --ttl <value>
  --traffic-policy-id <value>
  --traffic-policy-version <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--id`` (string)


  The ID of the traffic policy instance that you want to update.

  

``--ttl`` (long)


  The ttl that you want Amazon Route 53 to assign to all of the updated resource record sets.

  

``--traffic-policy-id`` (string)


  The ID of the traffic policy that you want Amazon Route 53 to use to update resource record sets for the specified traffic policy instance.

  

``--traffic-policy-version`` (integer)


  The version of the traffic policy that you want Amazon Route 53 to use to update resource record sets for the specified traffic policy instance.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

TrafficPolicyInstance -> (structure)

  

  A complex type that contains settings for the updated traffic policy instance.

  

  Id -> (string)

    

    

  HostedZoneId -> (string)

    

    

  Name -> (string)

    

    

  TTL -> (long)

    

    

  State -> (string)

    

    

  Message -> (string)

    

    

  TrafficPolicyId -> (string)

    

    

  TrafficPolicyVersion -> (integer)

    

    

  TrafficPolicyType -> (string)

    

    

  

