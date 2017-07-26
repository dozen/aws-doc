[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 list-reusable-delegation-sets:


*****************************
list-reusable-delegation-sets
*****************************



===========
Description
===========



Retrieves a list of the reusable delegation sets that are associated with the current AWS account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53-2013-04-01/ListReusableDelegationSets>`_


========
Synopsis
========

::

    list-reusable-delegation-sets
  [--marker <value>]
  [--max-items <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--marker`` (string)


  If the value of ``IsTruncated`` in the previous response was ``true`` , you have more reusable delegation sets. To get another group, submit another ``list-reusable-delegation-sets`` request. 

   

  For the value of ``marker`` , specify the value of ``NextMarker`` from the previous response, which is the ID of the first reusable delegation set that Amazon Route 53 will return if you submit another request.

   

  If the value of ``IsTruncated`` in the previous response was ``false`` , there are no more reusable delegation sets to get.

  

``--max-items`` (string)


  The number of reusable delegation sets that you want Amazon Route 53 to return in the response to this request. If you specify a value greater than 100, Amazon Route 53 returns only the first 100 reusable delegation sets.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

DelegationSets -> (list)

  

  A complex type that contains one ``DelegationSet`` element for each reusable delegation set that was created by the current AWS account.

  

  (structure)

    

    A complex type that lists the name servers in a delegation set, as well as the ``CallerReference`` and the ``ID`` for the delegation set.

    

    Id -> (string)

      

      The ID that Amazon Route 53 assigns to a reusable delegation set.

      

      

    CallerReference -> (string)

      

      The value that you specified for ``CallerReference`` when you created the reusable delegation set.

      

      

    NameServers -> (list)

      

      A complex type that contains a list of the authoritative name servers for a hosted zone or for a reusable delegation set.

      

      (string)

        

        

      

    

  

Marker -> (string)

  

  For the second and subsequent calls to ``list-reusable-delegation-sets`` , ``Marker`` is the value that you specified for the ``marker`` parameter in the request that produced the current response.

  

  

IsTruncated -> (boolean)

  

  A flag that indicates whether there are more reusable delegation sets to be listed.

  

  

NextMarker -> (string)

  

  If ``IsTruncated`` is ``true`` , the value of ``NextMarker`` identifies the next reusable delegation set that Amazon Route 53 will return if you submit another ``list-reusable-delegation-sets`` request and specify the value of ``NextMarker`` in the ``marker`` parameter.

  

  

MaxItems -> (string)

  

  The value that you specified for the ``maxitems`` parameter in the call to ``list-reusable-delegation-sets`` that produced the current response.

  

  

