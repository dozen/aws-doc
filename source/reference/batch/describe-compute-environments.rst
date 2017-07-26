[ :ref:`aws <cli:aws>` . :ref:`batch <cli:aws batch>` ]

.. _cli:aws batch describe-compute-environments:


*****************************
describe-compute-environments
*****************************



===========
Description
===========



Describes one or more of your compute environments.

 

If you are using an unmanaged compute environment, you can use the ``DescribeComputeEnvironment`` operation to determine the ``ecsClusterArn`` that you should launch your Amazon ECS container instances into.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/batch-2016-08-10/DescribeComputeEnvironments>`_


========
Synopsis
========

::

    describe-compute-environments
  [--compute-environments <value>]
  [--max-results <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--compute-environments`` (list)


  A list of up to 100 compute environment names or full Amazon Resource Name (ARN) entries. 

  



Syntax::

  "string" "string" ...



``--max-results`` (integer)


  The maximum number of cluster results returned by ``describe-compute-environments`` in paginated output. When this parameter is used, ``describe-compute-environments`` only returns ``maxResults`` results in a single page along with a ``nextToken`` response element. The remaining results of the initial request can be seen by sending another ``describe-compute-environments`` request with the returned ``nextToken`` value. This value can be between 1 and 100. If this parameter is not used, then ``describe-compute-environments`` returns up to 100 results and a ``nextToken`` value if applicable.

  

``--next-token`` (string)


  The ``nextToken`` value returned from a previous paginated ``describe-compute-environments`` request where ``maxResults`` was used and the results exceeded the value of that parameter. Pagination continues from the end of the previous results that returned the ``nextToken`` value. This value is ``null`` when there are no more results to return.

   

  .. note::

     

    This token should be treated as an opaque identifier that is only used to retrieve the next items in a list and not for other programmatic purposes.

     

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To describe a compute environment**

This example describes the `P2OnDemand` compute environment.

Command::

  aws batch describe-compute-environments --compute-environments P2OnDemand

Output::

	{
	    "computeEnvironments": [
	        {
	            "status": "VALID",
	            "serviceRole": "arn:aws:iam::012345678910:role/AWSBatchServiceRole",
	            "computeEnvironmentArn": "arn:aws:batch:us-east-1:012345678910:compute-environment/P2OnDemand",
	            "computeResources": {
	                "subnets": [
	                    "subnet-220c0e0a",
	                    "subnet-1a95556d",
	                    "subnet-978f6dce"
	                ],
	                "tags": {
	                    "Name": "Batch Instance - P2OnDemand"
	                },
	                "desiredvCpus": 48,
	                "minvCpus": 0,
	                "instanceTypes": [
	                    "p2"
	                ],
	                "securityGroupIds": [
	                    "sg-cf5093b2"
	                ],
	                "instanceRole": "ecsInstanceRole",
	                "maxvCpus": 128,
	                "type": "EC2",
	                "ec2KeyPair": "id_rsa"
	            },
	            "statusReason": "ComputeEnvironment Healthy",
	            "ecsClusterArn": "arn:aws:ecs:us-east-1:012345678910:cluster/P2OnDemand_Batch_2c06f29d-d1fe-3a49-879d-42394c86effc",
	            "state": "ENABLED",
	            "computeEnvironmentName": "P2OnDemand",
	            "type": "MANAGED"
	        }
	    ]
	}


======
Output
======

computeEnvironments -> (list)

  

  The list of compute environments.

  

  (structure)

    

    An object representing an AWS Batch compute environment.

    

    computeEnvironmentName -> (string)

      

      The name of the compute environment. 

      

      

    computeEnvironmentArn -> (string)

      

      The Amazon Resource Name (ARN) of the compute environment. 

      

      

    ecsClusterArn -> (string)

      

      The Amazon Resource Name (ARN) of the underlying Amazon ECS cluster used by the compute environment. 

      

      

    type -> (string)

      

      The type of the compute environment.

      

      

    state -> (string)

      

      The state of the compute environment. The valid values are ``ENABLED`` or ``DISABLED`` . An ``ENABLED`` state indicates that you can register instances with the compute environment and that the associated instances can accept jobs. 

      

      

    status -> (string)

      

      The current status of the compute environment (for example, ``CREATING`` or ``VALID`` ).

      

      

    statusReason -> (string)

      

      A short, human-readable string to provide additional details about the current status of the compute environment.

      

      

    computeResources -> (structure)

      

      The compute resources defined for the compute environment. 

      

      type -> (string)

        

        The type of compute environment.

        

        

      minvCpus -> (integer)

        

        The minimum number of EC2 vCPUs that an environment should maintain. 

        

        

      maxvCpus -> (integer)

        

        The maximum number of EC2 vCPUs that an environment can reach. 

        

        

      desiredvCpus -> (integer)

        

        The desired number of EC2 vCPUS in the compute environment. 

        

        

      instanceTypes -> (list)

        

        The instances types that may launched.

        

        (string)

          

          

        

      imageId -> (string)

        

        The Amazon Machine Image (AMI) ID used for instances launched in the compute environment.

        

        

      subnets -> (list)

        

        The VPC subnets into which the compute resources are launched. 

        

        (string)

          

          

        

      securityGroupIds -> (list)

        

        The EC2 security group that is associated with instances launched in the compute environment. 

        

        (string)

          

          

        

      ec2KeyPair -> (string)

        

        The EC2 key pair that is used for instances launched in the compute environment.

        

        

      instanceRole -> (string)

        

        The Amazon ECS instance role applied to Amazon EC2 instances in a compute environment.

        

        

      tags -> (map)

        

        Key-value pair tags to be applied to resources that are launched in the compute environment. 

        

        key -> (string)

          

          

        value -> (string)

          

          

        

      bidPercentage -> (integer)

        

        The minimum percentage that a Spot Instance price must be when compared with the On-Demand price for that instance type before instances are launched. For example, if your bid percentage is 20%, then the Spot price must be below 20% of the current On-Demand price for that EC2 instance.

        

        

      spotIamFleetRole -> (string)

        

        The Amazon Resource Name (ARN) of the Amazon EC2 Spot Fleet IAM role applied to a ``SPOT`` compute environment.

        

        

      

    serviceRole -> (string)

      

      The service role associated with the compute environment that allows AWS Batch to make calls to AWS API operations on your behalf.

      

      

    

  

nextToken -> (string)

  

  The ``nextToken`` value to include in a future ``describe-compute-environments`` request. When the results of a ``describe-job-definitions`` request exceed ``maxResults`` , this value can be used to retrieve the next page of results. This value is ``null`` when there are no more results to return.

  

  

