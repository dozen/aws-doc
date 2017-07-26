[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 list-reusable-delegation-sets:


*****************************
list-reusable-delegation-sets
*****************************



===========
Description
===========



To retrieve a list of your reusable delegation sets, send a ``GET`` request to the ``/*Route 53 API version* /delegationset`` resource. The response to this request includes a ``DelegationSets`` element with zero, one, or multiple ``DelegationSet`` child elements. By default, the list of delegation sets is displayed on a single page. You can control the length of the page that is displayed by using the ``MaxItems`` parameter. You can use the ``Marker`` parameter to control the delegation set that the list begins with. 

 

.. note::

  Amazon Route 53 returns a maximum of 100 items. If you set MaxItems to a value greater than 100, Amazon Route 53 returns only the first 100.



========
Synopsis
========

::

    list-reusable-delegation-sets
  [--marker <value>]
  [--max-items <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--marker`` (string)


  If the request returned more than one page of results, submit another request and specify the value of ``NextMarker`` from the last response in the ``marker`` parameter to get the next page of results.

  

``--max-items`` (string)


  Specify the maximum number of reusable delegation sets to return per page of results.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

DelegationSets -> (list)

  

  A complex type that contains information about the reusable delegation sets associated with the current AWS account.

  

  (structure)

    

    A complex type that contains name server information.

    

    Id -> (string)

      

      

    CallerReference -> (string)

      

      

    NameServers -> (list)

      

      A complex type that contains the authoritative name servers for the hosted zone. Use the method provided by your domain registrar to add an NS record to your domain for each ``NameServer`` that is assigned to your hosted zone.

      

      (string)

        

        

      

    

  

Marker -> (string)

  

  If the request returned more than one page of results, submit another request and specify the value of ``NextMarker`` from the last response in the ``marker`` parameter to get the next page of results.

  

  

IsTruncated -> (boolean)

  

  A flag indicating whether there are more reusable delegation sets to be listed. If your results were truncated, you can make a follow-up request for the next page of results by using the ``Marker`` element.

   

  Valid Values: ``true`` | ``false`` 

  

  

NextMarker -> (string)

  

  Indicates where to continue listing reusable delegation sets. If  ListReusableDelegationSetsResponse$IsTruncated is ``true`` , make another request to ``list-reusable-delegation-sets`` and include the value of the ``NextMarker`` element in the ``Marker`` element to get the next page of results.

  

  

MaxItems -> (string)

  

  The maximum number of reusable delegation sets to be included in the response body. If the number of reusable delegation sets associated with this AWS account exceeds ``MaxItems`` , the value of  ListReusablDelegationSetsResponse$IsTruncated in the response is ``true`` . Call ``list-reusable-delegation-sets`` again and specify the value of  ListReusableDelegationSetsResponse$NextMarker in the  ListReusableDelegationSetsRequest$Marker element to get the next page of results.

  

  

