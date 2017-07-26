[ :ref:`aws <cli:aws>` . :ref:`appstream <cli:aws appstream>` ]

.. _cli:aws appstream describe-fleets:


***************
describe-fleets
***************



===========
Description
===========



If fleet names are provided, this operation describes the specified fleets; otherwise, all the fleets in the account are described.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/appstream-2016-12-01/DescribeFleets>`_


========
Synopsis
========

::

    describe-fleets
  [--names <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--names`` (list)


  The fleet names to describe. Use null to describe all the fleets for the AWS account.

  



Syntax::

  "string" "string" ...



``--next-token`` (string)


  The pagination token to use to retrieve the next page of results for this operation. If this value is null, it retrieves the first page.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Fleets -> (list)

  

  The list of fleet details.

  

  (structure)

    

    Contains the parameters for a fleet.

    

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

        

        

      

    

  

NextToken -> (string)

  

  The pagination token to use to retrieve the next page of results for this operation. If there are no more pages, this value is null.

  

  

