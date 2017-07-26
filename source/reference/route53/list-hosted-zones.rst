[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 list-hosted-zones:


*****************
list-hosted-zones
*****************



===========
Description
===========



To retrieve a list of your hosted zones, send a ``GET`` request to the ``/*Route 53 API version* /hostedzone`` resource. The response to this request includes a ``HostedZones`` element with zero, one, or multiple ``HostedZone`` child elements. By default, the list of hosted zones is displayed on a single page. You can control the length of the page that is displayed by using the ``MaxItems`` parameter. You can use the ``Marker`` parameter to control the hosted zone that the list begins with. 

 

.. note::

  Amazon Route 53 returns a maximum of 100 items. If you set MaxItems to a value greater than 100, Amazon Route 53 returns only the first 100.



``list-hosted-zones`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``HostedZones``


========
Synopsis
========

::

    list-hosted-zones
  [--max-items <value>]
  [--delegation-set-id <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--max-items`` (string)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--delegation-set-id`` (string)


``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (string)
 

  The size of each page.

   

  

  

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

**To list the hosted zones associated with the current AWS account**

The following ``list-hosted-zones`` command lists summary information about the first 100 hosted zones that are associated with the current AWS account.::

  aws route53 list-hosted-zones

If you have more than 100 hosted zones, or if you want to list them in groups smaller than 100, include the ``--maxitems`` parameter. For example, to list hosted zones one at a time, use the following command::

  aws route53 list-hosted-zones --max-items 1

To view information about the next hosted zone, take the value of ``NextToken`` from the response to the previous command, and include it in the ``--starting-token`` parameter, for example::

  aws route53 list-hosted-zones --max-items 1 --starting-token Z3M3LMPEXAMPLE



======
Output
======

HostedZones -> (list)

  

  A complex type that contains information about the hosted zones associated with the current AWS account.

  

  (structure)

    

    A complex type that contain information about the specified hosted zone.

    

    Id -> (string)

      

      The ID of the specified hosted zone.

      

      

    Name -> (string)

      

      The name of the domain. This must be a fully-specified domain, for example, www.example.com. The trailing dot is optional; Amazon Route 53 assumes that the domain name is fully qualified. This means that Amazon Route 53 treats www.example.com (without a trailing dot) and www.example.com. (with a trailing dot) as identical.

       

      This is the name you have registered with your DNS registrar. You should ask your registrar to change the authoritative name servers for your domain to the set of ``NameServers`` elements returned in ``DelegationSet`` .

      

      

    CallerReference -> (string)

      

      A unique string that identifies the request to create the hosted zone.

      

      

    Config -> (structure)

      

      A complex type that contains the ``Comment`` element.

      

      Comment -> (string)

        

        An optional comment about your hosted zone. If you don't want to specify a comment, you can omit the ``HostedZoneConfig`` and ``Comment`` elements from the XML document.

        

        

      PrivateZone -> (boolean)

        

        

      

    ResourceRecordSetCount -> (long)

      

      Total number of resource record sets in the hosted zone.

      

      

    

  

Marker -> (string)

  

  If the request returned more than one page of results, submit another request and specify the value of ``NextMarker`` from the last response in the ``marker`` parameter to get the next page of results.

  

  

IsTruncated -> (boolean)

  

  A flag indicating whether there are more hosted zones to be listed. If your results were truncated, you can make a follow-up request for the next page of results by using the ``Marker`` element.

   

  Valid Values: ``true`` | ``false`` 

  

  

NextMarker -> (string)

  

  Indicates where to continue listing hosted zones. If  ListHostedZonesResponse$IsTruncated is ``true`` , make another request to ``list-hosted-zones`` and include the value of the ``NextMarker`` element in the ``Marker`` element to get the next page of results.

  

  

MaxItems -> (string)

  

  The maximum number of hosted zones to be included in the response body. If the number of hosted zones associated with this AWS account exceeds ``MaxItems`` , the value of  ListHostedZonesResponse$IsTruncated in the response is ``true`` . Call ``list-hosted-zones`` again and specify the value of  ListHostedZonesResponse$NextMarker in the  ListHostedZonesRequest$Marker element to get the next page of results.

  

  

