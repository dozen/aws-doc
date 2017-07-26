[ :ref:`aws <cli:aws>` . :ref:`route53 <cli:aws route53>` ]

.. _cli:aws route53 delete-vpc-association-authorization:


************************************
delete-vpc-association-authorization
************************************



===========
Description
===========



Removes authorization to submit an ``associate-vpc-with-hosted-zone`` request to associate a specified vpc with a hosted zone that was created by a different account. You must use the account that created the hosted zone to submit a ``delete-vpc-association-authorization`` request.

 

.. warning::

   

  Sending this request only prevents the AWS account that created the vpc from associating the vpc with the Amazon Route 53 hosted zone in the future. If the vpc is already associated with the hosted zone, ``delete-vpc-association-authorization`` won't disassociate the vpc from the hosted zone. If you want to delete an existing association, use ``disassociate-vpc-from-hosted-zone`` .

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/route53-2013-04-01/DeleteVPCAssociationAuthorization>`_


========
Synopsis
========

::

    delete-vpc-association-authorization
  --hosted-zone-id <value>
  --vpc <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--hosted-zone-id`` (string)


  When removing authorization to associate a vpc that was created by one AWS account with a hosted zone that was created with a different AWS account, the ID of the hosted zone.

  

``--vpc`` (structure)


  When removing authorization to associate a vpc that was created by one AWS account with a hosted zone that was created with a different AWS account, a complex type that includes the ID and region of the VPC.

  



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

