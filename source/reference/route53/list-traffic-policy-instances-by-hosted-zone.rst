[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 list-traffic-policy-instances-by-hosted-zone:


********************************************
list-traffic-policy-instances-by-hosted-zone
********************************************



===========
Description
===========



Gets information about the traffic policy instances that you created in a specified hosted zone.

 

.. note::

  After you submit an ``update-traffic-policy-instance`` request, there's a brief delay while Amazon Route 53 creates the resource record sets that are specified in the traffic policy definition. For more information, see the  State response element.

 

To get information about the traffic policy instances that you created in a specified hosted zone, send a ``GET`` request to the ``/*Route 53 API version* /trafficpolicyinstance`` resource and include the ID of the hosted zone.

 

Amazon Route 53 returns a maximum of 100 items in each response. If you have a lot of traffic policy instances, you can use the ``MaxItems`` parameter to list them in groups of up to 100.

 

The response includes four values that help you navigate from one group of ``MaxItems`` traffic policy instances to the next:

 

 
* **IsTruncated** 
 

If the value of ```` IsTruncated in the response is ``true`` , there are more traffic policy instances associated with the current AWS account.

 

If ``IsTruncated`` is ``false`` , this response includes the last traffic policy instance that is associated with the current account.

 
* **MaxItems** 
 

The value that you specified for the ``MaxItems`` parameter in the request that produced the current response.

 
* **TrafficPolicyInstanceNameMarker** and **TrafficPolicyInstanceTypeMarker** 
 

If ``IsTruncated`` is ``true`` , these two values in the response represent the first traffic policy instance in the next group of ``MaxItems`` traffic policy instances. To list more traffic policy instances, make another call to ``list-traffic-policy-instances-by-hosted-zone`` , and specify these values in the corresponding request parameters.

 

If ``IsTruncated`` is ``false`` , all three elements are omitted from the response.

 



========
Synopsis
========

::

    list-traffic-policy-instances-by-hosted-zone
  --hosted-zone-id <value>
  [--traffic-policy-instance-name-marker <value>]
  [--traffic-policy-instance-type-marker <value>]
  [--max-items <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--hosted-zone-id`` (string)


  The ID of the hosted zone for which you want to list traffic policy instances.

  

``--traffic-policy-instance-name-marker`` (string)


  For the first request to ``list-traffic-policy-instances-by-hosted-zone`` , omit this value.

   

  If the value of ``IsTruncated`` in the previous response was ``true`` , ``TrafficPolicyInstanceNameMarker`` is the name of the first traffic policy instance in the next group of ``MaxItems`` traffic policy instances.

   

  If the value of ``IsTruncated`` in the previous response was ``false`` , there are no more traffic policy instances to get for this hosted zone.

   

  If the value of ``IsTruncated`` in the previous response was ``false`` , omit this value.

  

``--traffic-policy-instance-type-marker`` (string)


  For the first request to ``list-traffic-policy-instances-by-hosted-zone`` , omit this value.

   

  If the value of ``IsTruncated`` in the previous response was ``true`` , ``TrafficPolicyInstanceTypeMarker`` is the DNS type of the first traffic policy instance in the next group of ``MaxItems`` traffic policy instances.

   

  If the value of ``IsTruncated`` in the previous response was ``false`` , there are no more traffic policy instances to get for this hosted zone.

  

  Possible values:

  
  *   ``SOA``

  
  *   ``A``

  
  *   ``TXT``

  
  *   ``NS``

  
  *   ``CNAME``

  
  *   ``MX``

  
  *   ``PTR``

  
  *   ``SRV``

  
  *   ``SPF``

  
  *   ``AAAA``

  

  

``--max-items`` (string)


  The maximum number of traffic policy instances to be included in the response body for this request. If you have more than ``MaxItems`` traffic policy instances, the value of the ``IsTruncated`` element in the response is ``true`` , and the values of ``HostedZoneIdMarker`` , ``TrafficPolicyInstanceNameMarker`` , and ``TrafficPolicyInstanceTypeMarker`` represent the first traffic policy instance in the next group of ``MaxItems`` traffic policy instances.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

TrafficPolicyInstances -> (list)

  

  A list that contains one ``TrafficPolicyInstance`` element for each traffic policy instance that matches the elements in the request. 

  

  (structure)

    

    Id -> (string)

      

      

    HostedZoneId -> (string)

      

      

    Name -> (string)

      

      

    TTL -> (long)

      

      

    State -> (string)

      

      

    Message -> (string)

      

      

    TrafficPolicyId -> (string)

      

      

    TrafficPolicyVersion -> (integer)

      

      

    TrafficPolicyType -> (string)

      

      

    

  

TrafficPolicyInstanceNameMarker -> (string)

  

  If ``IsTruncated`` is ``true`` , ``TrafficPolicyInstanceNameMarker`` is the name of the first traffic policy instance in the next group of ``MaxItems`` traffic policy instances.

  

  

TrafficPolicyInstanceTypeMarker -> (string)

  

  If ``IsTruncated`` is true, ``TrafficPolicyInstanceTypeMarker`` is the DNS type of the resource record sets that are associated with the first traffic policy instance in the next group of ``MaxItems`` traffic policy instances.

  

  

IsTruncated -> (boolean)

  

  A flag that indicates whether there are more traffic policy instances to be listed. If the response was truncated, you can get the next group of ``MaxItems`` traffic policy instances by calling ``list-traffic-policy-instances-by-hosted-zone`` again and specifying the values of the ``HostedZoneIdMarker`` , ``TrafficPolicyInstanceNameMarker`` , and ``TrafficPolicyInstanceTypeMarker`` elements in the corresponding request parameters.

   

  Valid Values: ``true`` | ``false`` 

  

  

MaxItems -> (string)

  

  The value that you specified for the ``MaxItems`` parameter in the call to ``list-traffic-policy-instances-by-hosted-zone`` that produced the current response. 

  

  
