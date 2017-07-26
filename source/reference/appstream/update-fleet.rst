[ :ref:`aws <cli:aws>` . :ref:`appstream <cli:aws appstream>` ]

.. _cli:aws appstream update-fleet:


************
update-fleet
************



===========
Description
===========



Updates an existing fleet. All the attributes except the fleet name can be updated in the **STOPPED** state. When a fleet is in the **RUNNING** state, only ``display-name`` and ``compute-capacity`` can be updated. A fleet cannot be updated in a status of **STARTING** or **STOPPING** .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/appstream-2016-12-01/UpdateFleet>`_


========
Synopsis
========

::

    update-fleet
  [--image-name <value>]
  --name <value>
  [--instance-type <value>]
  [--compute-capacity <value>]
  [--vpc-config <value>]
  [--max-user-duration-in-seconds <value>]
  [--disconnect-timeout-in-seconds <value>]
  [--delete-vpc-config | --no-delete-vpc-config]
  [--description <value>]
  [--display-name <value>]
  [--enable-default-internet-access | --no-enable-default-internet-access]
  [--domain-join-info <value>]
  [--attributes-to-delete <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--image-name`` (string)


  The image name from which a fleet is created.

  

``--name`` (string)


  The name of the fleet.

  

``--instance-type`` (string)


  The instance type of compute resources for the fleet. Fleet instances are launched from this instance type. Available instance types are:

   

   
  * stream.standard.medium 
   
  * stream.standard.large 
   
  * stream.compute.large 
   
  * stream.compute.xlarge 
   
  * stream.compute.2xlarge 
   
  * stream.compute.4xlarge 
   
  * stream.compute.8xlarge 
   
  * stream.memory.large 
   
  * stream.memory.xlarge 
   
  * stream.memory.2xlarge 
   
  * stream.memory.4xlarge 
   
  * stream.memory.8xlarge 
   

  

``--compute-capacity`` (structure)


  The parameters for the capacity allocated to the fleet. 

  



Shorthand Syntax::

    DesiredInstances=integer




JSON Syntax::

  {
    "DesiredInstances": integer
  }



``--vpc-config`` (structure)


  The VPC configuration for the fleet.

  



Shorthand Syntax::

    SubnetIds=string,string,SecurityGroupIds=string,string




JSON Syntax::

  {
    "SubnetIds": ["string", ...],
    "SecurityGroupIds": ["string", ...]
  }



``--max-user-duration-in-seconds`` (integer)


  The maximum time for which a streaming session can run. The input can be any numeric value in seconds between 600 and 57600.

  

``--disconnect-timeout-in-seconds`` (integer)


  The time after disconnection when a session is considered to have ended. If a user who got disconnected reconnects within this timeout interval, the user is connected back to their previous session. The input can be any numeric value in seconds between 60 and 57600.

  

``--delete-vpc-config`` | ``--no-delete-vpc-config`` (boolean)


  Delete the VPC association for the specified fleet.

  

``--description`` (string)


  The description displayed to end users on the AppStream 2.0 portal.

  

``--display-name`` (string)


  The name displayed to end users on the AppStream 2.0 portal.

  

``--enable-default-internet-access`` | ``--no-enable-default-internet-access`` (boolean)


  Enables or disables default internet access for the fleet.

  

``--domain-join-info`` (structure)


  The *DirectoryName* and *OrganizationalUnitDistinguishedName* values, which are used to join domains for the AppStream 2.0 streaming instances.

  



Shorthand Syntax::

    DirectoryName=string,OrganizationalUnitDistinguishedName=string




JSON Syntax::

  {
    "DirectoryName": "string",
    "OrganizationalUnitDistinguishedName": "string"
  }



``--attributes-to-delete`` (list)


  Fleet attributes to be deleted.

  



Syntax::

  "string" "string" ...

  Where valid values are:
    VPC_CONFIGURATION
    VPC_CONFIGURATION_SECURITY_GROUP_IDS
    DOMAIN_JOIN_INFO





``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Fleet -> (structure)

  

  A list of fleet details.

  

  Arn -> (string)

    

    The ARN for the fleet.

    

    

  Name -> (string)

    

    The name of the fleet.

    

    

  DisplayName -> (string)

    

    The name displayed to end users on the AppStream 2.0 portal.

    

    

  Description -> (string)

    

    The description displayed to end users on the AppStream 2.0 portal.

    

    

  ImageName -> (string)

    

    The image used by the fleet.

    

    

  InstanceType -> (string)

    

    The instance type of compute resources for the fleet. The fleet instances are launched from this instance type. 

    

    

  ComputeCapacityStatus -> (structure)

    

    The capacity information for the fleet.

    

    Desired -> (integer)

      

      The desired number of streaming instances.

      

      

    Running -> (integer)

      

      The total number of simultaneous streaming instances that are running.

      

      

    InUse -> (integer)

      

      The number of instances that are being used for streaming.

      

      

    Available -> (integer)

      

      The number of currently available instances that can be used to stream sessions.

      

      

    

  MaxUserDurationInSeconds -> (integer)

    

    The maximum time for which a streaming session can run. The value can be any numeric value in seconds between 600 and 57600.

    

    

  DisconnectTimeoutInSeconds -> (integer)

    

    The time after disconnection when a session is considered to have ended. If a user who got disconnected reconnects within this timeout interval, the user is connected back to their previous session. The input can be any numeric value in seconds between 60 and 57600.

    

    

  State -> (string)

    

    The current state for the fleet.

    

    

  VpcConfig -> (structure)

    

    The VPC configuration for the fleet.

    

    SubnetIds -> (list)

      

      The list of subnets to which a network interface is established from the fleet instance.

      

      (string)

        

        

      

    SecurityGroupIds -> (list)

      

      Security groups associated with the fleet.

      

      (string)

        

        

      

    

  CreatedTime -> (timestamp)

    

    The time at which the fleet was created.

    

    

  FleetErrors -> (list)

    

    The list of fleet errors is appended to this list.

    

    (structure)

      

      The details of the fleet error.

      

      ErrorCode -> (string)

        

        The error code for the fleet error.

        

        

      ErrorMessage -> (string)

        

        The error message generated when the fleet has errors.

        

        

      

    

  EnableDefaultInternetAccess -> (boolean)

    

    Whether default internet access is enabled for the fleet. 

    

    

  DomainJoinInfo -> (structure)

    

    The *DirectoryName* and *OrganizationalUnitDistinguishedName* values, which are used to join domains for the AppStream 2.0 streaming instances.

    

    DirectoryName -> (string)

      

      The fully qualified name of the directory, such as corp.example.com

      

      

    OrganizationalUnitDistinguishedName -> (string)

      

      The distinguished name of the organizational unit to place the computer account in.

      

      

    

  

