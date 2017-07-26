[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift describe-ec2-instance-limits:


****************************
describe-ec2-instance-limits
****************************



===========
Description
===========



Retrieves the following information for the specified EC2 instance type:

 

 
* maximum number of instances allowed per AWS account (service limit) 
 
* current usage level for the AWS account 
 

 

Service limits vary depending on region. Available regions for Amazon GameLift can be found in the AWS Management Console for Amazon GameLift (see the drop-down list in the upper right corner).

 

Fleet-related operations include:

 

 
*  create-fleet   
 
*  list-fleets   
 
* Describe fleets: 

   
  *  describe-fleet-attributes   
   
  *  describe-fleet-port-settings   
   
  *  describe-fleet-utilization   
   
  *  describe-runtime-configuration   
   
  *  describe-fleet-events   
   

 
 
* Update fleets: 

   
  *  update-fleet-attributes   
   
  *  update-fleet-capacity   
   
  *  update-fleet-port-settings   
   
  *  update-runtime-configuration   
   

 
 
* Manage fleet capacity: 

   
  *  describe-fleet-capacity   
   
  *  update-fleet-capacity   
   
  *  put-scaling-policy (automatic scaling) 
   
  *  describe-scaling-policies (automatic scaling) 
   
  *  delete-scaling-policy (automatic scaling) 
   
  *  describe-ec2-instance-limits   
   

 
 
*  delete-fleet   
 



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/gamelift-2015-10-01/DescribeEC2InstanceLimits>`_


========
Synopsis
========

::

    describe-ec2-instance-limits
  [--ec2-instance-type <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--ec2-instance-type`` (string)


  Name of an EC2 instance type that is supported in Amazon GameLift. A fleet instance type determines the computing resources of each instance in the fleet, including CPU, memory, storage, and networking capacity. Amazon GameLift supports the following EC2 instance types. See `Amazon EC2 Instance Types <http://aws.amazon.com/ec2/instance-types/>`_ for detailed descriptions. Leave this parameter blank to retrieve limits for all types.

  

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

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

EC2InstanceLimits -> (list)

  

  Object that contains the maximum number of instances for the specified instance type.

  

  (structure)

    

    Maximum number of instances allowed based on the Amazon Elastic Compute Cloud (Amazon EC2) instance type. Instance limits can be retrieved by calling  describe-ec2-instance-limits .

    

    EC2InstanceType -> (string)

      

      Name of an EC2 instance type that is supported in Amazon GameLift. A fleet instance type determines the computing resources of each instance in the fleet, including CPU, memory, storage, and networking capacity. Amazon GameLift supports the following EC2 instance types. See `Amazon EC2 Instance Types <http://aws.amazon.com/ec2/instance-types/>`_ for detailed descriptions.

      

      

    CurrentInstances -> (integer)

      

      Number of instances of the specified type that are currently in use by this AWS account.

      

      

    InstanceLimit -> (integer)

      

      Number of instances allowed.

      

      

    

  

