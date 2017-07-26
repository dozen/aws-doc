[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-vpc-endpoint-services:


******************************
describe-vpc-endpoint-services
******************************



===========
Description
===========



Describes all supported AWS services that can be specified when creating a VPC endpoint.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeVpcEndpointServices>`_


========
Synopsis
========

::

    describe-vpc-endpoint-services
  [--dry-run | --no-dry-run]
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--max-results`` (integer)


  The maximum number of items to return for this request. The request returns a token that you can specify in a subsequent call to get the next set of results.

   

  Constraint: If the value is greater than 1000, we return only 1000 items.

  

``--next-token`` (string)


  The token for the next set of items to return. (You received this token from a prior call.)

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe VPC endpoint services**

This example describes all available endpoint services for the region.

Command::

  aws ec2 describe-vpc-endpoint-services

Output::

  {
    "ServiceNames": [
      "com.amazonaws.us-east-1.s3"
    ]
  }

======
Output
======

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  

ServiceNames -> (list)

  

  A list of supported AWS services.

  

  (string)

    

    

  

