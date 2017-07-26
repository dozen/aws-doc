[ :ref:`aws <cli:aws>` . :ref:`dax <cli:aws dax>` ]

.. _cli:aws dax decrease-replication-factor:


***************************
decrease-replication-factor
***************************



===========
Description
===========



Removes one or more nodes from a DAX cluster.

 

.. note::

   

  You cannot use ``decrease-replication-factor`` to remove the last node in a DAX cluster. If you need to do this, use ``delete-cluster`` instead.

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/dax-2017-04-19/DecreaseReplicationFactor>`_


========
Synopsis
========

::

    decrease-replication-factor
  --cluster-name <value>
  --new-replication-factor <value>
  [--availability-zones <value>]
  [--node-ids-to-remove <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cluster-name`` (string)


  The name of the DAX cluster from which you want to remove nodes.

  

``--new-replication-factor`` (integer)


  The new number of nodes for the DAX cluster.

  

``--availability-zones`` (list)


  The Availability Zone(s) from which to remove nodes.

  



Syntax::

  "string" "string" ...



``--node-ids-to-remove`` (list)


  The unique identifiers of the nodes to be removed from the cluster.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



======
Output
======

Cluster -> (structure)

  

  A description of the DAX cluster, after you have decreased its replication factor.

  

  ClusterName -> (string)

    

    The name of the DAX cluster.

    

    

  Description -> (string)

    

    The description of the cluster.

    

    

  ClusterArn -> (string)

    

    The Amazon Resource Name (ARN) that uniquely identifies the cluster. 

    

    

  TotalNodes -> (integer)

    

    The total number of nodes in the cluster.

    

    

  ActiveNodes -> (integer)

    

    The number of nodes in the cluster that are active (i.e., capable of serving requests).

    

    

  NodeType -> (string)

    

    The node type for the nodes in the cluster. (All nodes in a DAX cluster are of the same type.)

    

    

  Status -> (string)

    

    The current status of the cluster.

    

    

  ClusterDiscoveryEndpoint -> (structure)

    

    The configuration endpoint for this DAX cluster, consisting of a DNS name and a port number. Client applications can specify this endpoint, rather than an individual node endpoint, and allow the DAX client software to intelligently route requests and responses to nodes in the DAX cluster.

    

    Address -> (string)

      

      The DNS hostname of the endpoint.

      

      

    Port -> (integer)

      

      The port number that applications should use to connect to the endpoint.

      

      

    

  NodeIdsToRemove -> (list)

    

    A list of nodes to be removed from the cluster.

    

    (string)

      

      

    

  Nodes -> (list)

    

    A list of nodes that are currently in the cluster.

    

    (structure)

      

      Represents an individual node within a DAX cluster.

      

      NodeId -> (string)

        

        A system-generated identifier for the node.

        

        

      Endpoint -> (structure)

        

        The endpoint for the node, consisting of a DNS name and a port number. Client applications can connect directly to a node endpoint, if desired (as an alternative to allowing DAX client software to intelligently route requests and responses to nodes in the DAX cluster.

        

        Address -> (string)

          

          The DNS hostname of the endpoint.

          

          

        Port -> (integer)

          

          The port number that applications should use to connect to the endpoint.

          

          

        

      NodeCreateTime -> (timestamp)

        

        The date and time (in UNIX epoch format) when the node was launched.

        

        

      AvailabilityZone -> (string)

        

        The Availability Zone (AZ) in which the node has been deployed.

        

        

      NodeStatus -> (string)

        

        The current status of the node. For example: ``available`` .

        

        

      ParameterGroupStatus -> (string)

        

        The status of the parameter group associated with this node. For example, ``in-sync`` .

        

        

      

    

  PreferredMaintenanceWindow -> (string)

    

    A range of time when maintenance of DAX cluster software will be performed. For example: ``sun:01:00-sun:09:00`` . Cluster maintenance normally takes less than 30 minutes, and is performed automatically within the maintenance window.

    

    

  NotificationConfiguration -> (structure)

    

    Describes a notification topic and its status. Notification topics are used for publishing DAX events to subscribers using Amazon Simple Notification Service (SNS).

    

    TopicArn -> (string)

      

      The Amazon Resource Name (ARN) that identifies the topic. 

      

      

    TopicStatus -> (string)

      

      The current state of the topic.

      

      

    

  SubnetGroup -> (string)

    

    The subnet group where the DAX cluster is running.

    

    

  SecurityGroups -> (list)

    

    A list of security groups, and the status of each, for the nodes in the cluster.

    

    (structure)

      

      An individual VPC security group and its status.

      

      SecurityGroupIdentifier -> (string)

        

        The unique ID for this security group.

        

        

      Status -> (string)

        

        The status of this security group.

        

        

      

    

  IamRoleArn -> (string)

    

    A valid Amazon Resource Name (ARN) that identifies an IAM role. At runtime, DAX will assume this role and use the role's permissions to access DynamoDB on your behalf.

    

    

  ParameterGroup -> (structure)

    

    The parameter group being used by nodes in the cluster.

    

    ParameterGroupName -> (string)

      

      The name of the parameter group.

      

      

    ParameterApplyStatus -> (string)

      

      The status of parameter updates. 

      

      

    NodeIdsToReboot -> (list)

      

      The node IDs of one or more nodes to be rebooted.

      

      (string)

        

        

      

    

  

