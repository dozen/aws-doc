[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 list-traffic-policy-versions:


****************************
list-traffic-policy-versions
****************************



===========
Description
===========



Gets information about all of the versions for a specified traffic policy. ``list-traffic-policy-versions`` lists only versions that have not been deleted.

 

Amazon Route 53 returns a maximum of 100 items in each response. If you have a lot of traffic policies, you can use the ``maxitems`` parameter to list them in groups of up to 100.

 

The response includes three values that help you navigate from one group of ``maxitems`` maxitems traffic policies to the next:

 

 
* **IsTruncated** 
 

If the value of ``IsTruncated`` in the response is ``true`` , there are more traffic policy versions associated with the specified traffic policy.

 

If ``IsTruncated`` is ``false`` , this response includes the last traffic policy version that is associated with the specified traffic policy.

 
* **traffic-policy-version-marker** 
 

The ID of the next traffic policy version that is associated with the current AWS account. If you want to list more traffic policies, make another call to ``list-traffic-policy-versions`` , and specify the value of the ``traffic-policy-version-marker`` element in the ``traffic-policy-version-marker`` request parameter.

 

If ``IsTruncated`` is ``false`` , Amazon Route 53 omits the ``traffic-policy-version-marker`` element from the response.

 
* **MaxItems** 
 

The value that you specified for the ``MaxItems`` parameter in the request that produced the current response.

 



========
Synopsis
========

::

    list-traffic-policy-versions
  --id <value>
  [--traffic-policy-version-marker <value>]
  [--max-items <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--id`` (string)


  Specify the value of ``Id`` of the traffic policy for which you want to list all versions.

  

``--traffic-policy-version-marker`` (string)


  For your first request to ``list-traffic-policy-versions`` , do not include the ``traffic-policy-version-marker`` parameter.

   

  If you have more traffic policy versions than the value of ``MaxItems`` , ``list-traffic-policy-versions`` returns only the first group of ``MaxItems`` versions. To get the next group of ``MaxItems`` traffic policy versions, submit another request to ``list-traffic-policy-versions`` . For the value of ``traffic-policy-version-marker`` , specify the value of the ``traffic-policy-version-marker`` element that was returned in the previous response.

   

  Traffic policy versions are listed in sequential order.

  

``--max-items`` (string)


  The maximum number of traffic policy versions that you want Amazon Route 53 to include in the response body for this request. If the specified traffic policy has more than ``MaxItems`` versions, the value of the ``IsTruncated`` element in the response is ``true`` , and the value of the ``traffic-policy-version-marker`` element is the ID of the first version in the next group of ``MaxItems`` traffic policy versions.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

TrafficPolicies -> (list)

  

  A list that contains one ``TrafficPolicy`` element for each traffic policy version that is associated with the specified traffic policy.

  

  (structure)

    

    Id -> (string)

      

      

    Version -> (integer)

      

      

    Name -> (string)

      

      

    Type -> (string)

      

      

    Document -> (string)

      

      

    Comment -> (string)

      

      

    

  

IsTruncated -> (boolean)

  

  A flag that indicates whether there are more traffic policies to be listed. If the response was truncated, you can get the next group of ``maxitems`` traffic policies by calling ``list-traffic-policy-versions`` again and specifying the value of the ``NextMarker`` element in the marker parameter.

   

  Valid Values: ``true`` | ``false`` 

  

  

TrafficPolicyVersionMarker -> (string)

  

  If ``IsTruncated`` is ``true`` , the value of ``traffic-policy-version-marker`` identifies the first traffic policy in the next group of ``MaxItems`` traffic policies. Call ``list-traffic-policy-versions`` again and specify the value of ``traffic-policy-version-marker`` in the ``traffic-policy-version-marker`` request parameter.

   

  This element is present only if ``IsTruncated`` is ``true`` .

  

  

MaxItems -> (string)

  

  The value that you specified for the ``maxitems`` parameter in the call to ``list-traffic-policy-versions`` that produced the current response.

  

  

