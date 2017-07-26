[ :ref:`aws <cli:aws>` . :ref:`gamelift <cli:aws gamelift>` ]

.. _cli:aws gamelift describe-instances:


******************
describe-instances
******************



===========
Description
===========



Retrieves information about a fleet's instances, including instance IDs. Use this action to get details on all instances in the fleet or get details on one specific instance.

 

To get a specific instance, specify fleet ID and instance ID. To get all instances in a fleet, specify a fleet ID only. Use the pagination parameters to retrieve results as a set of sequential pages. If successful, an  Instance object is returned for each result.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/gamelift-2015-10-01/DescribeInstances>`_


========
Synopsis
========

::

    describe-instances
  --fleet-id <value>
  [--instance-id <value>]
  [--limit <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--fleet-id`` (string)


  Unique identifier for a fleet to retrieve instance information for.

  

``--instance-id`` (string)


  Unique identifier for an instance to retrieve. Specify an instance ID or leave blank to retrieve all instances in the fleet.

  

``--limit`` (integer)


  Maximum number of results to return. Use this parameter with ``NextToken`` to get results as a set of sequential pages.

  

``--next-token`` (string)


  Token that indicates the start of the next sequential page of results. Use the token that is returned with a previous call to this action. To specify the start of the result set, do not specify a value.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Instances -> (list)

  

  Collection of objects containing properties for each instance returned.

  

  (structure)

    

    Properties that describe an instance of a virtual computing resource that hosts one or more game servers. A fleet contains zero or more instances.

    

    FleetId -> (string)

      

      Unique identifier for a fleet that the instance is in.

      

      

    InstanceId -> (string)

      

      Unique identifier for an instance.

      

      

    IpAddress -> (string)

      

      IP address assigned to the instance.

      

      

    OperatingSystem -> (string)

      

      Operating system that is running on this instance. 

      

      

    Type -> (string)

      

      EC2 instance type that defines the computing resources of this instance. 

      

      

    Status -> (string)

      

      Current status of the instance. Possible statuses include the following:

       

       
      * **PENDING** – The instance is in the process of being created and launching server processes as defined in the fleet's run-time configuration.  
       
      * **ACTIVE** – The instance has been successfully created and at least one server process has successfully launched and reported back to Amazon GameLift that it is ready to host a game session. The instance is now considered ready to host game sessions.  
       
      * **TERMINATING** – The instance is in the process of shutting down. This may happen to reduce capacity during a scaling down event or to recycle resources in the event of a problem. 
       

      

      

    CreationTime -> (timestamp)

      

      Time stamp indicating when this data object was created. Format is a number expressed in Unix time as milliseconds (for example "1469498468.057").

      

      

    

  

NextToken -> (string)

  

  Token that indicates where to resume retrieving results on the next call to this action. If no token is returned, these results represent the end of the list.

  

  

