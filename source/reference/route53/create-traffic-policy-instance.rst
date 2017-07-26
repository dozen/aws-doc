[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 create-traffic-policy-instance:


******************************
create-traffic-policy-instance
******************************



===========
Description
===========



Creates resource record sets in a specified hosted zone based on the settings in a specified traffic policy version. In addition, ``create-traffic-policy-instance`` associates the resource record sets with a specified domain name (such as example.com) or subdomain name (such as www.example.com). Amazon Route 53 responds to DNS queries for the domain or subdomain name by using the resource record sets that ``create-traffic-policy-instance`` created.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53-2013-04-01/CreateTrafficPolicyInstance>`_


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
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--hosted-zone-id`` (string)


  The ID of the hosted zone in which you want Amazon Route 53 to create resource record sets by using the configuration in a traffic policy.

  

``--name`` (string)


  The domain name (such as example.com) or subdomain name (such as www.example.com) for which Amazon Route 53 responds to DNS queries by using the resource record sets that Amazon Route 53 creates for this traffic policy instance.

  

``--ttl`` (long)


  (Optional) The ttl that you want Amazon Route 53 to assign to all of the resource record sets that it creates in the specified hosted zone.

  

``--traffic-policy-id`` (string)


  The ID of the traffic policy that you want to use to create resource record sets in the specified hosted zone.

  

``--traffic-policy-version`` (integer)


  The version of the traffic policy that you want to use to create resource record sets in the specified hosted zone.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

TrafficPolicyInstance -> (structure)

  

  A complex type that contains settings for the new traffic policy instance.

  

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

    

    

  

Location -> (string)

  

  A unique URL that represents a new traffic policy instance.

  

  

