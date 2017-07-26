[ :ref:`aws <cli:aws>` . :ref:`ec2 <cli:aws ec2>` ]

.. _cli:aws ec2 describe-classic-link-instances:


*******************************
describe-classic-link-instances
*******************************



===========
Description
===========



Describes one or more of your linked EC2-Classic instances. This request only returns information about EC2-Classic instances linked to a VPC through ClassicLink; you cannot use this request to return information about other instances.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/ec2-2016-11-15/DescribeClassicLinkInstances>`_


========
Synopsis
========

::

    describe-classic-link-instances
  [--filters <value>]
  [--dry-run | --no-dry-run]
  [--instance-ids <value>]
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--filters`` (list)


  One or more filters.

   

   
  * ``group-id`` - The ID of a VPC security group that's associated with the instance. 
   
  * ``instance-id`` - The ID of the instance. 
   
  * ``tag`` :*key* =*value* - The key/value combination of a tag assigned to the resource. 
   
  * ``tag-key`` - The key of a tag assigned to the resource. This filter is independent of the ``tag-value`` filter. For example, if you use both the filter "tag-key=Purpose" and the filter "tag-value=X", you get any resources assigned both the tag key Purpose (regardless of what the tag's value is), and the tag value X (regardless of what the tag's key is). If you want to list only resources where Purpose is X, see the ``tag`` :*key* =*value* filter. 
   
  * ``tag-value`` - The value of a tag assigned to the resource. This filter is independent of the ``tag-key`` filter. 
   
  * ``vpc-id`` - The ID of the VPC that the instance is linked to. 
   

  



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

  

``--instance-ids`` (list)


  One or more instance IDs. Must be instances linked to a VPC through ClassicLink.

  



Syntax::

  "string" "string" ...



``--max-results`` (integer)


  The maximum number of results to return for the request in a single page. The remaining results of the initial request can be seen by sending another request with the returned ``NextToken`` value. This value can be between 5 and 1000; if ``MaxResults`` is given a value larger than 1000, only 1000 results are returned. You cannot specify this parameter and the instance IDs parameter in the same request.

   

  Constraint: If the value is greater than 1000, we return only 1000 items.

  

``--next-token`` (string)


  The token to retrieve the next page of results.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe linked EC2-Classic instances**

This example lists all of your linked EC2-Classic instances.

Command::

  aws ec2 describe-classic-link-instances

Output::

	{
		"Instances": [
			{
				"InstanceId": "i-1234567890abcdef0", 
				"VpcId": "vpc-88888888", 
				"Groups": [
					{
						"GroupId": "sg-11122233"
					}                   
				], 
				"Tags": [
					{
						"Value": "ClassicInstance", 
						"Key": "Name"
					}
				]
			}, 
			{
				"InstanceId": "i-0598c7d356eba48d7", 
				"VpcId": "vpc-12312312", 
				"Groups": [
					{
						"GroupId": "sg-aabbccdd"
					}  
				], 
				"Tags": [
					{
						"Value": "ClassicInstance2", 
						"Key": "Name"
					}
				]
			}
		]
	}
	
This example lists all of your linked EC2-Classic instances, and filters the response to include only instances that are linked to VPC vpc-88888888.

Command::

  aws ec2 describe-classic-link-instances --filter "Name=vpc-id,Values=vpc-88888888"

Output::

	{
		"Instances": [
			{
				"InstanceId": "i-1234567890abcdef0", 
				"VpcId": "vpc-88888888", 
				"Groups": [
					{
						"GroupId": "sg-11122233"
					}                   
				], 
				"Tags": [
					{
						"Value": "ClassicInstance", 
						"Key": "Name"
					}
				]
			}
		]
	}


======
Output
======

Instances -> (list)

  

  Information about one or more linked EC2-Classic instances.

  

  (structure)

    

    Describes a linked EC2-Classic instance.

    

    Groups -> (list)

      

      A list of security groups.

      

      (structure)

        

        Describes a security group.

        

        GroupName -> (string)

          

          The name of the security group.

          

          

        GroupId -> (string)

          

          The ID of the security group.

          

          

        

      

    InstanceId -> (string)

      

      The ID of the instance.

      

      

    Tags -> (list)

      

      Any tags assigned to the instance.

      

      (structure)

        

        Describes a tag.

        

        Key -> (string)

          

          The key of the tag.

           

          Constraints: Tag keys are case-sensitive and accept a maximum of 127 Unicode characters. May not begin with ``aws:``  

          

          

        Value -> (string)

          

          The value of the tag.

           

          Constraints: Tag values are case-sensitive and accept a maximum of 255 Unicode characters.

          

          

        

      

    VpcId -> (string)

      

      The ID of the VPC.

      

      

    

  

NextToken -> (string)

  

  The token to use to retrieve the next page of results. This value is ``null`` when there are no more results to return.

  

  

