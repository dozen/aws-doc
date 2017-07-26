[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 list-traffic-policy-versions:


****************************
list-traffic-policy-versions
****************************



===========
Description
===========



Gets information about all of the versions for a specified traffic policy.

 

Traffic policy versions are listed in numerical order by ``VersionNumber`` .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53-2013-04-01/ListTrafficPolicyVersions>`_


========
Synopsis
========

::

    list-traffic-policy-versions
  --id <value>
  [--traffic-policy-version-marker <value>]
  [--max-items <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--id`` (string)


  Specify the value of ``Id`` of the traffic policy for which you want to list all versions.

  

``--traffic-policy-version-marker`` (string)


  For your first request to ``list-traffic-policy-versions`` , don't include the ``traffic-policy-version-marker`` parameter.

   

  If you have more traffic policy versions than the value of ``MaxItems`` , ``list-traffic-policy-versions`` returns only the first group of ``MaxItems`` versions. To get more traffic policy versions, submit another ``list-traffic-policy-versions`` request. For the value of ``traffic-policy-version-marker`` , specify the value of ``traffic-policy-version-marker`` in the previous response.

  

``--max-items`` (string)


  The maximum number of traffic policy versions that you want Amazon Route 53 to include in the response body for this request. If the specified traffic policy has more than ``MaxItems`` versions, the value of ``IsTruncated`` in the response is ``true`` , and the value of the ``traffic-policy-version-marker`` element is the ID of the first version that Amazon Route 53 will return if you submit another request.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

TrafficPolicies -> (list)

  

  A list that contains one ``TrafficPolicy`` element for each traffic policy version that is associated with the specified traffic policy.

  

  (structure)

    

    A complex type that contains settings for a traffic policy.

    

    Id -> (string)

      

      The ID that Amazon Route 53 assigned to a traffic policy when you created it.

      

      

    Version -> (integer)

      

      The version number that Amazon Route 53 assigns to a traffic policy. For a new traffic policy, the value of ``Version`` is always 1.

      

      

    Name -> (string)

      

      The name that you specified when you created the traffic policy.

      

      

    Type -> (string)

      

      The DNS type of the resource record sets that Amazon Route 53 creates when you use a traffic policy to create a traffic policy instance.

      

      

    Document -> (string)

      

      The definition of a traffic policy in JSON format. You specify the JSON document to use for a new traffic policy in the ``create-traffic-policy`` request. For more information about the JSON format, see `Traffic Policy Document Format <http://docs.aws.amazon.com/Route53/latest/APIReference/api-policies-traffic-policy-document-format.html>`_ .

      

      

    Comment -> (string)

      

      The comment that you specify in the ``create-traffic-policy`` request, if any.

      

      

    

  

IsTruncated -> (boolean)

  

  A flag that indicates whether there are more traffic policies to be listed. If the response was truncated, you can get the next group of traffic policies by submitting another ``list-traffic-policy-versions`` request and specifying the value of ``NextMarker`` in the ``marker`` parameter.

  

  

TrafficPolicyVersionMarker -> (string)

  

  If ``IsTruncated`` is ``true`` , the value of ``traffic-policy-version-marker`` identifies the first traffic policy that Amazon Route 53 will return if you submit another request. Call ``list-traffic-policy-versions`` again and specify the value of ``traffic-policy-version-marker`` in the ``traffic-policy-version-marker`` request parameter.

   

  This element is present only if ``IsTruncated`` is ``true`` .

  

  

MaxItems -> (string)

  

  The value that you specified for the ``maxitems`` parameter in the ``list-traffic-policy-versions`` request that produced the current response.

  

  

