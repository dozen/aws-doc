[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-moving-addresses:


*************************
describe-moving-addresses
*************************



===========
Description
===========



Describes your Elastic IP addresses that are being moved to the EC2-VPC platform, or that are being restored to the EC2-Classic platform. This request does not return information about any other Elastic IP addresses in your account.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeMovingAddresses>`_


========
Synopsis
========

::

    describe-moving-addresses
  [--filters <value>]
  [--dry-run | --no-dry-run]
  [--max-results <value>]
  [--next-token <value>]
  [--public-ips <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filters`` (list)


  One or more filters.

   

   
  * ``moving-status`` - The status of the Elastic IP address (``MovingToVpc`` | ``RestoringToClassic`` ). 
   

  



Shorthand Syntax::

    Name=string,Values=string,string ...




JSON Syntax::

  [
    {
      "Name": "string",
      "Values": ["string", ...]
    }
    ...
  ]



``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--max-results`` (integer)


  The maximum number of results to return for the request in a single page. The remaining results of the initial request can be seen by sending another request with the returned ``NextToken`` value. This value can be between 5 and 1000; if ``MaxResults`` is given a value outside of this range, an error is returned.

   

  Default: If no value is provided, the default is 1000.

  

``--next-token`` (string)


  The token to use to retrieve the next page of results.

  

``--public-ips`` (list)


  One or more Elastic IP addresses.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe your moving addresses**

This example describes all of your moving Elastic IP addresses.

Command::

  aws ec2 describe-moving-addresses

Output::

  {
    "MovingAddressStatuses": [
      {
        "PublicIp": "198.51.100.0",
        "MoveStatus": "MovingToVpc"
      }
    ]
  }

This example describes all addresses that are moving to the EC2-VPC platform.

Command::

  aws ec2 describe-moving-addresses --filters Name=moving-status,Values=MovingToVpc

======
Output
======

MovingAddressStatuses -> (list)

  

  The status for each Elastic IP address.

  

  (structure)

    

    Describes the status of a moving Elastic IP address.

    

    MoveStatus -> (string)

      

      The status of the Elastic IP address that's being moved to the EC2-VPC platform, or restored to the EC2-Classic platform.

      

      

    PublicIp -> (string)

      

      The Elastic IP address.

      

      

    

  

NextToken -> (string)

  

  The token to use to retrieve the next page of results. This value is ``null`` when there are no more results to return.

  

  

