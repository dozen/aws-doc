[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 list-traffic-policies:


*********************
list-traffic-policies
*********************



===========
Description
===========



Gets information about the latest version for every traffic policy that is associated with the current AWS account. To get the information, send a ``GET`` request to the ``/*Route 53 API version* /trafficpolicy`` resource.

 

Amazon Route 53 returns a maximum of 100 items in each response. If you have a lot of traffic policies, you can use the ``maxitems`` parameter to list them in groups of up to 100.

 

The response includes three values that help you navigate from one group of ``maxitems`` traffic policies to the next:

 

 
* **IsTruncated** 
 

If the value of ``IsTruncated`` in the response is ``true`` , there are more traffic policies associated with the current AWS account.

 

If ``IsTruncated`` is ``false`` , this response includes the last traffic policy that is associated with the current account.

 
* **TrafficPolicyIdMarker** 
 

If ``IsTruncated`` is ``true`` , ``TrafficPolicyIdMarker`` is the ID of the first traffic policy in the next group of ``MaxItems`` traffic policies. If you want to list more traffic policies, make another call to ``list-traffic-policies`` , and specify the value of the ``TrafficPolicyIdMarker`` element from the response in the ``TrafficPolicyIdMarker`` request parameter.

 

If ``IsTruncated`` is ``false`` , the ``TrafficPolicyIdMarker`` element is omitted from the response.

 
* **MaxItems** 
 

The value that you specified for the ``MaxItems`` parameter in the request that produced the current response.

 



========
Synopsis
========

::

    list-traffic-policies
  [--traffic-policy-id-marker <value>]
  [--max-items <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--traffic-policy-id-marker`` (string)


  For your first request to ``list-traffic-policies`` , do not include the ``TrafficPolicyIdMarker`` parameter.

   

  If you have more traffic policies than the value of ``MaxItems`` , ``list-traffic-policies`` returns only the first ``MaxItems`` traffic policies. To get the next group of ``MaxItems`` policies, submit another request to ``list-traffic-policies`` . For the value of ``TrafficPolicyIdMarker`` , specify the value of the ``TrafficPolicyIdMarker`` element that was returned in the previous response.

   

  Policies are listed in the order in which they were created.

  

``--max-items`` (string)


  The maximum number of traffic policies to be included in the response body for this request. If you have more than ``MaxItems`` traffic policies, the value of the ``IsTruncated`` element in the response is ``true`` , and the value of the ``TrafficPolicyIdMarker`` element is the ID of the first traffic policy in the next group of ``MaxItems`` traffic policies.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

TrafficPolicySummaries -> (list)

  

  A list that contains one ``TrafficPolicySummary`` element for each traffic policy that was created by the current AWS account.

  

  (structure)

    

    Id -> (string)

      

      

    Name -> (string)

      

      

    Type -> (string)

      

      

    LatestVersion -> (integer)

      

      

    TrafficPolicyCount -> (integer)

      

      

    

  

IsTruncated -> (boolean)

  

  A flag that indicates whether there are more traffic policies to be listed. If the response was truncated, you can get the next group of ``MaxItems`` traffic policies by calling ``list-traffic-policies`` again and specifying the value of the ``TrafficPolicyIdMarker`` element in the ``TrafficPolicyIdMarker`` request parameter.

   

  Valid Values: ``true`` | ``false`` 

  

  

TrafficPolicyIdMarker -> (string)

  

  If the value of ``IsTruncated`` is ``true`` , ``TrafficPolicyIdMarker`` is the ID of the first traffic policy in the next group of ``MaxItems`` traffic policies.

  

  

MaxItems -> (string)

  

  The value that you specified for the ``MaxItems`` parameter in the call to ``list-traffic-policies`` that produced the current response.

  

  

