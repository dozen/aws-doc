[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 list-vpc-association-authorizations:


***********************************
list-vpc-association-authorizations
***********************************



===========
Description
===========



Gets a list of the VPCs that were created by other accounts and that can be associated with a specified hosted zone because you've submitted one or more ``create-vpc-association-authorization`` requests. 

 

The response includes a ``VPCs`` element with a ``VPC`` child element for each VPC that can be associated with the hosted zone.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53-2013-04-01/ListVPCAssociationAuthorizations>`_


========
Synopsis
========

::

    list-vpc-association-authorizations
  --hosted-zone-id <value>
  [--next-token <value>]
  [--max-results <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--hosted-zone-id`` (string)


  The ID of the hosted zone for which you want a list of VPCs that can be associated with the hosted zone.

  

``--next-token`` (string)


   *Optional* : If a response includes a ``NextToken`` element, there are more VPCs that can be associated with the specified hosted zone. To get the next page of results, submit another request, and include the value of ``NextToken`` from the response in the ``nexttoken`` parameter in another ``list-vpc-association-authorizations`` request.

  

``--max-results`` (string)


   *Optional* : An integer that specifies the maximum number of VPCs that you want Amazon Route 53 to return. If you don't specify a value for ``max-results`` , Amazon Route 53 returns up to 50 VPCs per page.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

HostedZoneId -> (string)

  

  The ID of the hosted zone that you can associate the listed VPCs with.

  

  

NextToken -> (string)

  

  When the response includes a ``NextToken`` element, there are more VPCs that can be associated with the specified hosted zone. To get the next page of VPCs, submit another ``list-vpc-association-authorizations`` request, and include the value of the ``NextToken`` element from the response in the ``nexttoken`` request parameter.

  

  

VPCs -> (list)

  

  The list of VPCs that are authorized to be associated with the specified hosted zone.

  

  (structure)

    

    (Private hosted zones only) A complex type that contains information about an Amazon VPC.

    

    VPCRegion -> (string)

      

      (Private hosted zones only) The region in which you created an Amazon VPC.

      

      

    VPCId -> (string)

      

      (Private hosted zones only) The ID of an Amazon VPC. 

      

      

    

  

