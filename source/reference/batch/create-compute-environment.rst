[ :ref:`aws <cli:aws>` . :ref:`batch <cli:aws batch>` ]

.. _cli:aws batch create-compute-environment:


**************************
create-compute-environment
**************************



===========
Description
===========



Creates an AWS Batch compute environment. You can create ``MANAGED`` or ``UNMANAGED`` compute environments.

 

In a managed compute environment, AWS Batch manages the compute resources within the environment, based on the compute resources that you specify. Instances launched into a managed compute environment use the latest Amazon ECS-optimized AMI. You can choose to use Amazon EC2 On-Demand instances in your managed compute environment, or you can use Amazon EC2 Spot instances that only launch when the Spot bid price is below a specified percentage of the On-Demand price.

 

In an unmanaged compute environment, you can manage your own compute resources. This provides more compute resource configuration options, such as using a custom AMI, but you must ensure that your AMI meets the Amazon ECS container instance AMI specification. For more information, see `Container Instance AMIs <http://docs.aws.amazon.com/AmazonECS/latest/developerguide/container_instance_AMIs.html>`_ in the *Amazon EC2 Container Service Developer Guide* . After you have created your unmanaged compute environment, you can use the  describe-compute-environments operation to find the Amazon ECS cluster that is associated with it and then manually launch your container instances into that Amazon ECS cluster. For more information, see `Launching an Amazon ECS Container Instance <http://docs.aws.amazon.com/AmazonECS/latest/developerguide/launch_container_instance.html>`_ in the *Amazon EC2 Container Service Developer Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/batch-2016-08-10/CreateComputeEnvironment>`_


========
Synopsis
========

::

    create-compute-environment
  --compute-environment-name <value>
  --type <value>
  [--state <value>]
  [--compute-resources <value>]
  --service-role <value>
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--compute-environment-name`` (string)


  The name for your compute environment. Up to 128 letters (uppercase and lowercase), numbers, and underscores are allowed.

  

``--type`` (string)


  The type of the compute environment. 

  

  Possible values:

  
  *   ``MANAGED``

  
  *   ``UNMANAGED``

  

  

``--state`` (string)


  The state of the compute environment. If the state is ``ENABLED`` , then the compute environment accepts jobs from a queue and can scale out automatically based on queues.

  

  Possible values:

  
  *   ``ENABLED``

  
  *   ``DISABLED``

  

  

``--compute-resources`` (structure)


  Details of the compute resources managed by the compute environment. This parameter is required for managed compute environments.

  



Shorthand Syntax::

    type=string,minvCpus=integer,maxvCpus=integer,desiredvCpus=integer,instanceTypes=string,string,imageId=string,subnets=string,string,securityGroupIds=string,string,ec2KeyPair=string,instanceRole=string,tags={KeyName1=string,KeyName2=string},bidPercentage=integer,spotIamFleetRole=string




JSON Syntax::

  {
    "type": "EC2"|"SPOT",
    "minvCpus": integer,
    "maxvCpus": integer,
    "desiredvCpus": integer,
    "instanceTypes": ["string", ...],
    "imageId": "string",
    "subnets": ["string", ...],
    "securityGroupIds": ["string", ...],
    "ec2KeyPair": "string",
    "instanceRole": "string",
    "tags": {"string": "string"
      ...},
    "bidPercentage": integer,
    "spotIamFleetRole": "string"
  }



``--service-role`` (string)


  The full Amazon Resource Name (ARN) of the IAM role that allows AWS Batch to make calls to other AWS services on your behalf. 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To create a managed compute environment with On-Demand instances**

This example creates a managed compute environment with specific C4 instance types that are launched on demand. The compute environment is called `C4OnDemand`.

Command::

  aws batch create-compute-environment --cli-input-json file://<path_to_json_file>/C4OnDemand.json
  
JSON file format::

  {
    "computeEnvironmentName": "C4OnDemand",
    "type": "MANAGED",
    "state": "ENABLED",
    "computeResources": {
      "type": "EC2",
      "minvCpus": 0,
      "maxvCpus": 128,
      "desiredvCpus": 48,
      "instanceTypes": [
        "c4.large",
        "c4.xlarge",
        "c4.2xlarge",
        "c4.4xlarge",
        "c4.8xlarge"
      ],
      "subnets": [
        "subnet-220c0e0a",
        "subnet-1a95556d",
        "subnet-978f6dce"
      ],
      "securityGroupIds": [
        "sg-cf5093b2"
      ],
      "ec2KeyPair": "id_rsa",
      "instanceRole": "ecsInstanceRole",
      "tags": {
        "Name": "Batch Instance - C4OnDemand"
      }
    },
    "serviceRole": "arn:aws:iam::012345678910:role/AWSBatchServiceRole"
  }

Output::

  {
      "computeEnvironmentName": "C4OnDemand",
      "computeEnvironmentArn": "arn:aws:batch:us-east-1:012345678910:compute-environment/C4OnDemand"
  }

**To create a managed compute environment with Spot Instances**

This example creates a managed compute environment with the M4 instance type that is launched when the Spot bid price is at or below 20% of the On-Demand price for the instance type. The compute environment is called `M4Spot`.

Command::

  aws batch create-compute-environment --cli-input-json file://<path_to_json_file>/M4Spot.json
  
JSON file format::

  {
    "computeEnvironmentName": "M4Spot",
    "type": "MANAGED",
    "state": "ENABLED",
    "computeResources": {
      "type": "SPOT",
      "spotIamFleetRole": "arn:aws:iam::012345678910:role/aws-ec2-spot-fleet-role",
      "minvCpus": 0,
      "maxvCpus": 128,
      "desiredvCpus": 4,
      "instanceTypes": [
        "m4"
      ],
      "bidPercentage": 20,
      "subnets": [
        "subnet-220c0e0a",
        "subnet-1a95556d",
        "subnet-978f6dce"
      ],
      "securityGroupIds": [
        "sg-cf5093b2"
      ],
      "ec2KeyPair": "id_rsa",
      "instanceRole": "ecsInstanceRole",
      "tags": {
        "Name": "Batch Instance - M4Spot"
      }
    },
    "serviceRole": "arn:aws:iam::012345678910:role/AWSBatchServiceRole"
  }

Output::

  {
      "computeEnvironmentName": "M4Spot",
      "computeEnvironmentArn": "arn:aws:batch:us-east-1:012345678910:compute-environment/M4Spot"
  }


======
Output
======

computeEnvironmentName -> (string)

  

  The name of the compute environment.

  

  

computeEnvironmentArn -> (string)

  

  The Amazon Resource Name (ARN) of the compute environment. 

  

  

