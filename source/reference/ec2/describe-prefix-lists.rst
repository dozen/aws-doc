[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-prefix-lists:


*********************
describe-prefix-lists
*********************



===========
Description
===========



Describes available AWS services in a prefix list format, which includes the prefix list name and prefix list ID of the service and the IP address range for the service. A prefix list ID is required for creating an outbound security group rule that allows traffic from a VPC to access an AWS service through a VPC endpoint.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribePrefixLists>`_


========
Synopsis
========

::

    describe-prefix-lists
  [--dry-run | --no-dry-run]
  [--filters <value>]
  [--max-results <value>]
  [--next-token <value>]
  [--prefix-list-ids <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--dry-run`` | ``--no-dry-run`` (boolean)


  Checks whether you have the required permissions for the action, without actually making the request, and provides an error response. If you have the required permissions, the error response is ``DryRunOperation`` . Otherwise, it is ``UnauthorizedOperation`` .

  

``--filters`` (list)


  One or more filters.

   

   
  * ``prefix-list-id`` : The ID of a prefix list. 
   
  * ``prefix-list-name`` : The name of a prefix list. 
   

  



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



``--max-results`` (integer)


  The maximum number of items to return for this request. The request returns a token that you can specify in a subsequent call to get the next set of results.

   

  Constraint: If the value specified is greater than 1000, we return only 1000 items.

  

``--next-token`` (string)


  The token for the next set of items to return. (You received this token from a prior call.)

  

``--prefix-list-ids`` (list)


  One or more prefix list IDs.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe prefix lists**

This example lists all available prefix lists for the region.

Command::

  aws ec2 describe-prefix-lists

Output::

  {
    "PrefixLists": [
      {
        "PrefixListName": "com.amazonaws.us-east-1.s3", 
        "Cidrs": [
          "54.231.0.0/17"
        ], 
        "PrefixListId": "pl-63a5400a"
      }
    ]
  }


======
Output
======

NextToken -> (string)

  

  The token to use when requesting the next set of items. If there are no additional items to return, the string is empty.

  

  

PrefixLists -> (list)

  

  All available prefix lists.

  

  (structure)

    

    Describes prefixes for AWS services.

    

    Cidrs -> (list)

      

      The IP address range of the AWS service.

      

      (string)

        

        

      

    PrefixListId -> (string)

      

      The ID of the prefix.

      

      

    PrefixListName -> (string)

      

      The name of the prefix.

      

      

    

  

