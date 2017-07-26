[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 create-vpc-association-authorization:


************************************
create-vpc-association-authorization
************************************



===========
Description
===========



Authorizes the AWS account that created a specified vpc to submit an ``associate-vpc-with-hosted-zone`` request to associate the vpc with a specified hosted zone that was created by a different account. To submit a ``create-vpc-association-authorization`` request, you must use the account that created the hosted zone. After you authorize the association, use the account that created the vpc to submit an ``associate-vpc-with-hosted-zone`` request.

 

.. note::

   

  If you want to associate multiple VPCs that you created by using one account with a hosted zone that you created by using a different account, you must submit one authorization request for each VPC.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53-2013-04-01/CreateVPCAssociationAuthorization>`_


========
Synopsis
========

::

    create-vpc-association-authorization
  --hosted-zone-id <value>
  --vpc <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--hosted-zone-id`` (string)


  The ID of the private hosted zone that you want to authorize associating a vpc with.

  

``--vpc`` (structure)


  A complex type that contains the vpc ID and region for the vpc that you want to authorize associating with your hosted zone.

  



Shorthand Syntax::

    VPCRegion=string,VPCId=string




JSON Syntax::

  {
    "VPCRegion": "us-east-1"|"us-east-2"|"us-west-1"|"us-west-2"|"eu-west-1"|"eu-west-2"|"eu-central-1"|"ap-southeast-1"|"ap-southeast-2"|"ap-south-1"|"ap-northeast-1"|"ap-northeast-2"|"sa-east-1"|"ca-central-1"|"cn-north-1",
    "VPCId": "string"
  }



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

HostedZoneId -> (string)

  

  The ID of the hosted zone that you authorized associating a vpc with.

  

  

VPC -> (structure)

  

  The vpc that you authorized associating with a hosted zone.

  

  VPCRegion -> (string)

    

    (Private hosted zones only) The region in which you created an Amazon VPC.

    

    

  VPCId -> (string)

    

    (Private hosted zones only) The ID of an Amazon VPC. 

    

    

  

