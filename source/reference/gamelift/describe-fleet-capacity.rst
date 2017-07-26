[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift describe-fleet-capacity:


***********************
describe-fleet-capacity
***********************



===========
Description
===========



Retrieves the current status of fleet capacity for one or more fleets. This information includes the number of instances that have been requested for the fleet and the number currently active. You can request capacity for all fleets, or specify a list of one or more fleet IDs. When requesting all fleets, use the pagination parameters to retrieve results as a set of sequential pages. If successful, a  FleetCapacity object is returned for each requested fleet ID. When specifying a list of fleet IDs, attribute objects are returned only for fleets that currently exist. 

 

.. note::

  

  Some API actions may limit the number of fleet IDs allowed in one request. If a request exceeds this limit, the request fails and the error message includes the maximum allowed.

  



========
Synopsis
========

::

    describe-fleet-capacity
  [--fleet-ids <value>]
  [--limit <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--fleet-ids`` (list)


  Unique identifier for the fleet(s) you want to retrieve capacity information for. 

  



Syntax::

  "string" "string" ...



``--limit`` (integer)


  Maximum number of results to return. You can use this parameter with *NextToken* to get results as a set of sequential pages. This parameter is ignored when the request specifies one or a list of fleet IDs.

  

``--next-token`` (string)


  Token indicating the start of the next sequential page of results. Use the token that is returned with a previous call to this action. To specify the start of the result set, do not specify a value. This parameter is ignored when the request specifies one or a list of fleet IDs.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



======
Output
======

FleetCapacity -> (list)

  

  Collection of objects containing capacity information for each requested fleet ID. Leave this parameter empty to retrieve capacity information for all fleets.

  

  (structure)

    

    Information about the fleet's capacity. Fleet capacity is measured in EC2 instances. By default, new fleets have a capacity of one instance, but can be updated as needed. The maximum number of instances for a fleet is determined by the fleet's instance type.

    

    FleetId -> (string)

      

      Unique identifier for a fleet.

      

      

    InstanceType -> (string)

      

      Type of EC2 instances used in the fleet. EC2 instance types define the CPU, memory, storage, and networking capacity of the fleetaposs hosts. Amazon GameLift supports the EC2 instance types listed below. See `Amazon EC2 Instance Types`_ for detailed descriptions of each.

      

      

    InstanceCounts -> (structure)

      

      Current status of fleet capacity.

      

      DESIRED -> (integer)

        

        Ideal number of active instances in the fleet.

        

        

      PENDING -> (integer)

        

        Number of instances in the fleet that are starting but not yet active.

        

        

      ACTIVE -> (integer)

        

        Actual number of active instances in the fleet.

        

        

      TERMINATING -> (integer)

        

        Number of instances in the fleet that are no longer active but haven't yet been terminated. 

        

        

      

    

  

NextToken -> (string)

  

  Token indicating where to resume retrieving results on the next call to this action. If no token is returned, these results represent the end of the list.

   

  .. note::

    

    If a request has a limit that exactly matches the number of remaining results, a token is returned even though there are no more results to retrieve.

    

  

  



.. _Amazon EC2 Instance Types: https://aws.amazon.com/ec2/instance-types/
