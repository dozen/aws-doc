[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 get-traffic-policy-instance:


***************************
get-traffic-policy-instance
***************************



===========
Description
===========



Gets information about a specified traffic policy instance.

 

.. note::

   

  After you submit a ``create-traffic-policy-instance`` or an ``update-traffic-policy-instance`` request, there's a brief delay while Amazon Route 53 creates the resource record sets that are specified in the traffic policy definition. For more information, see the ``State`` response element.

   

 

.. note::

   

  In the Amazon Route 53 console, traffic policy instances are known as policy records.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53-2013-04-01/GetTrafficPolicyInstance>`_


========
Synopsis
========

::

    get-traffic-policy-instance
  --id <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--id`` (string)


  The ID of the traffic policy instance that you want to get information about.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

TrafficPolicyInstance -> (structure)

  

  A complex type that contains settings for the traffic policy instance.

  

  Id -> (string)

    

    The ID that Amazon Route 53 assigned to the new traffic policy instance.

    

    

  HostedZoneId -> (string)

    

    The ID of the hosted zone that Amazon Route 53 created resource record sets in.

    

    

  Name -> (string)

    

    The DNS name, such as www.example.com, for which Amazon Route 53 responds to queries by using the resource record sets that are associated with this traffic policy instance. 

    

    

  TTL -> (long)

    

    The TTL that Amazon Route 53 assigned to all of the resource record sets that it created in the specified hosted zone.

    

    

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

    

    

  

