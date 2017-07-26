[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 list-traffic-policies:


*********************
list-traffic-policies
*********************



===========
Description
===========



Gets information about the latest version for every traffic policy that is associated with the current AWS account. Policies are listed in the order in which they were created. 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53-2013-04-01/ListTrafficPolicies>`_


========
Synopsis
========

::

    list-traffic-policies
  [--traffic-policy-id-marker <value>]
  [--max-items <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--traffic-policy-id-marker`` (string)


  (Conditional) For your first request to ``list-traffic-policies`` , don't include the ``TrafficPolicyIdMarker`` parameter.

   

  If you have more traffic policies than the value of ``MaxItems`` , ``list-traffic-policies`` returns only the first ``MaxItems`` traffic policies. To get the next group of policies, submit another request to ``list-traffic-policies`` . For the value of ``TrafficPolicyIdMarker`` , specify the value of ``TrafficPolicyIdMarker`` that was returned in the previous response.

  

``--max-items`` (string)


  (Optional) The maximum number of traffic policies that you want Amazon Route 53 to return in response to this request. If you have more than ``MaxItems`` traffic policies, the value of ``IsTruncated`` in the response is ``true`` , and the value of ``TrafficPolicyIdMarker`` is the ID of the first traffic policy that Amazon Route 53 will return if you submit another request.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

TrafficPolicySummaries -> (list)

  

  A list that contains one ``TrafficPolicySummary`` element for each traffic policy that was created by the current AWS account.

  

  (structure)

    

    A complex type that contains information about the latest version of one traffic policy that is associated with the current AWS account.

    

    Id -> (string)

      

      The ID that Amazon Route 53 assigned to the traffic policy when you created it.

      

      

    Name -> (string)

      

      The name that you specified for the traffic policy when you created it.

      

      

    Type -> (string)

      

      The DNS type of the resource record sets that Amazon Route 53 creates when you use a traffic policy to create a traffic policy instance.

      

      

    LatestVersion -> (integer)

      

      The version number of the latest version of the traffic policy.

      

      

    TrafficPolicyCount -> (integer)

      

      The number of traffic policies that are associated with the current AWS account.

      

      

    

  

IsTruncated -> (boolean)

  

  A flag that indicates whether there are more traffic policies to be listed. If the response was truncated, you can get the next group of traffic policies by submitting another ``list-traffic-policies`` request and specifying the value of ``TrafficPolicyIdMarker`` in the ``TrafficPolicyIdMarker`` request parameter.

  

  

TrafficPolicyIdMarker -> (string)

  

  If the value of ``IsTruncated`` is ``true`` , ``TrafficPolicyIdMarker`` is the ID of the first traffic policy in the next group of ``MaxItems`` traffic policies.

  

  

MaxItems -> (string)

  

  The value that you specified for the ``MaxItems`` parameter in the ``list-traffic-policies`` request that produced the current response.

  

  

