[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 update-traffic-policy-instance:


******************************
update-traffic-policy-instance
******************************



===========
Description
===========



Updates the resource record sets in a specified hosted zone that were created based on the settings in a specified traffic policy version.

 

When you update a traffic policy instance, Amazon Route 53 continues to respond to DNS queries for the root resource record set name (such as example.com) while it replaces one group of resource record sets with another. Amazon Route 53 performs the following operations:

 

 
* Amazon Route 53 creates a new group of resource record sets based on the specified traffic policy. This is true regardless of how significant the differences are between the existing resource record sets and the new resource record sets.  
 
* When all of the new resource record sets have been created, Amazon Route 53 starts to respond to DNS queries for the root resource record set name (such as example.com) by using the new resource record sets. 
 
* Amazon Route 53 deletes the old group of resource record sets that are associated with the root resource record set name. 
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53-2013-04-01/UpdateTrafficPolicyInstance>`_


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
  [--generate-cli-skeleton <value>]




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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

TrafficPolicyInstance -> (structure)

  

  A complex type that contains settings for the updated traffic policy instance.

  

  Id -> (string)

    

    The ID that Amazon Route 53 assigned to the new traffic policy instance.

    

    

  HostedZoneId -> (string)

    

    The ID of the hosted zone that Amazon Route 53 created resource record sets in.

    

    

  Name -> (string)

    

    The DNS name, such as www.example.com, for which Amazon Route 53 responds to queries by using the resource record sets that are associated with this traffic policy instance. 

    

    

  TTL -> (long)

    

    The ttl that Amazon Route 53 assigned to all of the resource record sets that it created in the specified hosted zone.

    

    

  State -> (string)

    

    The value of ``State`` is one of the following values:

      Applied  

    Amazon Route 53 has finished creating resource record sets, and changes have propagated to all Amazon Route 53 edge locations.

      Creating  

    Amazon Route 53 is creating the resource record sets. Use ``get-traffic-policy-instance`` to confirm that the ``create-traffic-policy-instance`` request completed successfully.

      Failed  

    Amazon Route 53 wasn't able to create or update the resource record sets. When the value of ``State`` is ``Failed`` , see ``Message`` for an explanation of what caused the request to fail.

      

    

  Message -> (string)

    

    If ``State`` is ``Failed`` , an explanation of the reason for the failure. If ``State`` is another value, ``Message`` is empty.

    

    

  TrafficPolicyId -> (string)

    

    The ID of the traffic policy that Amazon Route 53 used to create resource record sets in the specified hosted zone.

    

    

  TrafficPolicyVersion -> (integer)

    

    The version of the traffic policy that Amazon Route 53 used to create resource record sets in the specified hosted zone.

    

    

  TrafficPolicyType -> (string)

    

    The DNS type that Amazon Route 53 assigned to all of the resource record sets that it created for this traffic policy instance. 

    

    

  

