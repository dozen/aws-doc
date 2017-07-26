[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-egress-only-internet-gateways:


**************************************
describe-egress-only-internet-gateways
**************************************



===========
Description
===========



Describes one or more of your egress-only Internet gateways.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeEgressOnlyInternetGateways>`_


========
Synopsis
========

::

    describe-egress-only-internet-gateways
  [--dry-run | --no-dry-run]
  [--egress-only-internet-gateway-ids <value>]
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--egress-only-internet-gateway-ids`` (list)


  One or more egress-only Internet gateway IDs.

  



Syntax::

  "string" "string" ...



``--max-results`` (integer)


  The maximum number of results to return for the request in a single page. The remaining results can be seen by sending another request with the returned ``NextToken`` value. This value can be between 5 and 1000; if ``MaxResults`` is given a value larger than 1000, only 1000 results are returned.

  

``--next-token`` (string)


  The token to retrieve the next page of results.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe your egress-only Internet gateways**

This example describes your egress-only Internet gateways.

Command::

  aws ec2 describe-egress-only-internet-gateways

Output::

  {
    "EgressOnlyInternetGateways": [
        {
            "EgressOnlyInternetGatewayId": "eigw-015e0e244e24dfe8a", 
            "Attachments": [
                {
                    "State": "attached", 
                    "VpcId": "vpc-0c62a468"
                }
            ]
        }
    ]
  }

======
Output
======

EgressOnlyInternetGateways -> (list)

  

  Information about the egress-only Internet gateways.

  

  (structure)

    

    Describes an egress-only Internet gateway.

    

    Attachments -> (list)

      

      Information about the attachment of the egress-only Internet gateway.

      

      (structure)

        

        Describes the attachment of a VPC to an Internet gateway or an egress-only Internet gateway.

        

        State -> (string)

          

          The current state of the attachment.

          

          

        VpcId -> (string)

          

          The ID of the VPC.

          

          

        

      

    EgressOnlyInternetGatewayId -> (string)

      

      The ID of the egress-only Internet gateway.

      

      

    

  

NextToken -> (string)

  

  The token to use to retrieve the next page of results.

  

  

