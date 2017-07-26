[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift describe-ec2-instance-limits:


****************************
describe-ec2-instance-limits
****************************



===========
Description
===========



Retrieves the maximum number of instances allowed, per AWS account, for each specified EC2 instance type. The current usage level for the AWS account is also retrieved.



========
Synopsis
========

::

    describe-ec2-instance-limits
  [--ec2-instance-type <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--ec2-instance-type`` (string)


  Type of EC2 instances used in the fleet. EC2 instance types define the CPU, memory, storage, and networking capacity of the fleetaposs hosts. Amazon GameLift supports the EC2 instance types listed below. See `Amazon EC2 Instance Types`_ for detailed descriptions of each. Leave this parameter blank to retrieve limits for all types.

  

  Possible values:

  
  *   ``t2.micro``

  
  *   ``t2.small``

  
  *   ``t2.medium``

  
  *   ``t2.large``

  
  *   ``c3.large``

  
  *   ``c3.xlarge``

  
  *   ``c3.2xlarge``

  
  *   ``c3.4xlarge``

  
  *   ``c3.8xlarge``

  
  *   ``c4.large``

  
  *   ``c4.xlarge``

  
  *   ``c4.2xlarge``

  
  *   ``c4.4xlarge``

  
  *   ``c4.8xlarge``

  
  *   ``r3.large``

  
  *   ``r3.xlarge``

  
  *   ``r3.2xlarge``

  
  *   ``r3.4xlarge``

  
  *   ``r3.8xlarge``

  
  *   ``m3.medium``

  
  *   ``m3.large``

  
  *   ``m3.xlarge``

  
  *   ``m3.2xlarge``

  
  *   ``m4.large``

  
  *   ``m4.xlarge``

  
  *   ``m4.2xlarge``

  
  *   ``m4.4xlarge``

  
  *   ``m4.10xlarge``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

EC2InstanceLimits -> (list)

  

  Object containing the maximum number of instances for the specified instance type.

  

  (structure)

    

    Maximum number of instances allowed based on the Amazon Elastic Compute Cloud (Amazon EC2) instance type. Instance limits can be retrieved by calling  describe-ec2-instance-limits .

    

    EC2InstanceType -> (string)

      

      Type of EC2 instances used in the fleet. EC2 instance types define the CPU, memory, storage, and networking capacity of the fleetaposs hosts. Amazon GameLift supports the EC2 instance types listed below. See `Amazon EC2 Instance Types`_ for detailed descriptions of each.

      

      

    CurrentInstances -> (integer)

      

      Number of instances of the specified type that are currently in use by this AWS account. 

      

      

    InstanceLimit -> (integer)

      

      Number of instances allowed.

      

      

    

  



.. _Amazon EC2 Instance Types: https://aws.amazon.com/ec2/instance-types/
