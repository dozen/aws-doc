[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 list-hosted-zones:


*****************
list-hosted-zones
*****************



===========
Description
===========



Retrieves a list of the public and private hosted zones that are associated with the current AWS account. The response includes a ``HostedZones`` child element for each hosted zone.

 

Amazon Route 53 returns a maximum of 100 items in each response. If you have a lot of hosted zones, you can use the ``maxitems`` parameter to list them in groups of up to 100.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53-2013-04-01/ListHostedZones>`_


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
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--max-items`` (string)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--delegation-set-id`` (string)


  If you're using reusable delegation sets and you want to list all of the hosted zones that are associated with a reusable delegation set, specify the ID of that reusable delegation set. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (string)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

  

  A complex type that contains general information about the hosted zone.

  

  (structure)

    

    A complex type that contains general information about the hosted zone.

    

    Id -> (string)

      

      The ID that Amazon Route 53 assigned to the hosted zone when you created it.

      

      

    Name -> (string)

      

      The name of the domain. For public hosted zones, this is the name that you have registered with your DNS registrar.

       

      For information about how to specify characters other than ``a-z`` , ``0-9`` , and ``-`` (hyphen) and how to specify internationalized domain names, see  create-hosted-zone .

      

      

    CallerReference -> (string)

      

      The value that you specified for ``CallerReference`` when you created the hosted zone.

      

      

    Config -> (structure)

      

      A complex type that includes the ``Comment`` and ``PrivateZone`` elements. If you omitted the ``HostedZoneConfig`` and ``Comment`` elements from the request, the ``Config`` and ``Comment`` elements don't appear in the response.

      

      Comment -> (string)

        

        Any comments that you want to include about the hosted zone.

        

        

      PrivateZone -> (boolean)

        

        A value that indicates whether this is a private hosted zone.

        

        

      

    ResourceRecordSetCount -> (long)

      

      The number of resource record sets in the hosted zone.

      

      

    

  

Marker -> (string)

  

  For the second and subsequent calls to ``list-hosted-zones`` , ``Marker`` is the value that you specified for the ``marker`` parameter in the request that produced the current response.

  

  

IsTruncated -> (boolean)

  

  A flag indicating whether there are more hosted zones to be listed. If the response was truncated, you can get more hosted zones by submitting another ``list-hosted-zones`` request and specifying the value of ``NextMarker`` in the ``marker`` parameter.

  

  

NextMarker -> (string)

  

  If ``IsTruncated`` is ``true`` , the value of ``NextMarker`` identifies the first hosted zone in the next group of hosted zones. Submit another ``list-hosted-zones`` request, and specify the value of ``NextMarker`` from the response in the ``marker`` parameter.

   

  This element is present only if ``IsTruncated`` is ``true`` .

  

  

MaxItems -> (string)

  

  The value that you specified for the ``maxitems`` parameter in the call to ``list-hosted-zones`` that produced the current response.

  

  

