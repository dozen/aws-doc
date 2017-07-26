[ :ref:`aws <cli:aws>` . :ref:`dax <cli:aws dax>` ]

.. _cli:aws dax describe-subnet-groups:


**********************
describe-subnet-groups
**********************



===========
Description
===========



Returns a list of subnet group descriptions. If a subnet group name is specified, the list will contain only the description of that group.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dax-2017-04-19/DescribeSubnetGroups>`_


========
Synopsis
========

::

    describe-subnet-groups
  [--subnet-group-names <value>]
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--subnet-group-names`` (list)


  The name of the subnet group.

  



Syntax::

  "string" "string" ...



``--max-results`` (integer)


  The maximum number of results to include in the response. If more results exist than the specified ``MaxResults`` value, a token is included in the response so that the remaining results can be retrieved.

   

  The value for ``MaxResults`` must be between 20 and 100.

  

``--next-token`` (string)


  An optional token returned from a prior request. Use this token for pagination of results from this action. If this parameter is specified, the response includes only results beyond the token, up to the value specified by ``MaxResults`` .

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

NextToken -> (string)

  

  Provides an identifier to allow retrieval of paginated results.

  

  

SubnetGroups -> (list)

  

  An array of subnet groups. Each element in the array represents a single subnet group.

  

  (structure)

    

    Represents the output of one of the following actions:

     

     
    * *create-subnet-group*   
     
    * *ModifySubnetGroup*   
     

    

    SubnetGroupName -> (string)

      

      The name of the subnet group.

      

      

    Description -> (string)

      

      The description of the subnet group.

      

      

    VpcId -> (string)

      

      The Amazon Virtual Private Cloud identifier (VPC ID) of the subnet group.

      

      

    Subnets -> (list)

      

      A list of subnets associated with the subnet group. 

      

      (structure)

        

        Represents the subnet associated with a DAX cluster. This parameter refers to subnets defined in Amazon Virtual Private Cloud (Amazon VPC) and used with DAX.

        

        SubnetIdentifier -> (string)

          

          The system-assigned identifier for the subnet.

          

          

        SubnetAvailabilityZone -> (string)

          

          The Availability Zone (AZ) for subnet subnet.

          

          

        

      

    

  

