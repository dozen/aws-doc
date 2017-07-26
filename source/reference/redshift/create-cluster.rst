[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift create-cluster:


**************
create-cluster
**************



===========
Description
===========



Creates a new cluster. To create the cluster in virtual private cloud (VPC), you must provide cluster subnet group name. If you don't provide a cluster subnet group name or the cluster security group parameter, Amazon Redshift creates a non-VPC cluster, it associates the default cluster security group with the cluster. For more information about managing clusters, go to `Amazon Redshift Clusters`_ in the *Amazon Redshift Cluster Management Guide* . 



========
Synopsis
========

::

    create-cluster
  [--db-name <value>]
  --cluster-identifier <value>
  [--cluster-type <value>]
  --node-type <value>
  --master-username <value>
  --master-user-password <value>
  [--cluster-security-groups <value>]
  [--vpc-security-group-ids <value>]
  [--cluster-subnet-group-name <value>]
  [--availability-zone <value>]
  [--preferred-maintenance-window <value>]
  [--cluster-parameter-group-name <value>]
  [--automated-snapshot-retention-period <value>]
  [--port <value>]
  [--cluster-version <value>]
  [--allow-version-upgrade | --no-allow-version-upgrade]
  [--number-of-nodes <value>]
  [--publicly-accessible | --no-publicly-accessible]
  [--encrypted | --no-encrypted]
  [--hsm-client-certificate-identifier <value>]
  [--hsm-configuration-identifier <value>]
  [--elastic-ip <value>]
  [--tags <value>]
  [--kms-key-id <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--db-name`` (string)


  The name of the first database to be created when the cluster is created. 

   

  To create additional databases after the cluster is created, connect to the cluster with a SQL client and use SQL commands to create a database. For more information, go to `Create a Database`_ in the Amazon Redshift Database Developer Guide. 

   

  Default: ``dev`` 

   

  Constraints:

   

   
  * Must contain 1 to 64 alphanumeric characters.
   
  * Must contain only lowercase letters.
   
  * Cannot be a word that is reserved by the service. A list of reserved words can be found in `Reserved Words`_ in the Amazon Redshift Database Developer Guide. 
   

  

``--cluster-identifier`` (string)


  A unique identifier for the cluster. You use this identifier to refer to the cluster for any subsequent cluster operations such as deleting or modifying. The identifier also appears in the Amazon Redshift console. 

   

  Constraints:

   

   
  * Must contain from 1 to 63 alphanumeric characters or hyphens.
   
  * Alphabetic characters must be lowercase.
   
  * First character must be a letter.
   
  * Cannot end with a hyphen or contain two consecutive hyphens.
   
  * Must be unique for all clusters within an AWS account.
   

   

  Example: ``myexamplecluster`` 

  

``--cluster-type`` (string)


  The type of the cluster. When cluster type is specified as 

   
  * ``single-node`` , the **NumberOfNodes** parameter is not required.
   
  * ``multi-node`` , the **NumberOfNodes** parameter is required.
   

   

   

  Valid Values: ``multi-node`` | ``single-node``  

   

  Default: ``multi-node`` 

  

``--node-type`` (string)


  The node type to be provisioned for the cluster. For information about node types, go to `Working with Clusters`_ in the *Amazon Redshift Cluster Management Guide* . 

   

  Valid Values: ``ds1.xlarge`` | ``ds1.8xlarge`` | ``ds2.xlarge`` | ``ds2.8xlarge`` | ``dc1.large`` | ``dc1.8xlarge`` . 

  

``--master-username`` (string)


  The user name associated with the master user account for the cluster that is being created. 

   

  Constraints:

   

   
  * Must be 1 - 128 alphanumeric characters.
   
  * First character must be a letter.
   
  * Cannot be a reserved word. A list of reserved words can be found in `Reserved Words`_ in the Amazon Redshift Database Developer Guide. 
   

  

``--master-user-password`` (string)


  The password associated with the master user account for the cluster that is being created. 

   

  Constraints: 

   

   
  * Must be between 8 and 64 characters in length.
   
  * Must contain at least one uppercase letter.
   
  * Must contain at least one lowercase letter.
   
  * Must contain one number.
   
  * Can be any printable ASCII character (ASCII code 33 to 126) except ' (single quote), " (double quote), \, /, @, or space.
   

  

``--cluster-security-groups`` (list)


  A list of security groups to be associated with this cluster. 

   

  Default: The default cluster security group for Amazon Redshift. 

  



Syntax::

  "string" "string" ...



``--vpc-security-group-ids`` (list)


  A list of Virtual Private Cloud (VPC) security groups to be associated with the cluster.

   

  Default: The default VPC security group is associated with the cluster.

  



Syntax::

  "string" "string" ...



``--cluster-subnet-group-name`` (string)


  The name of a cluster subnet group to be associated with this cluster. 

   

  If this parameter is not provided the resulting cluster will be deployed outside virtual private cloud (VPC). 

  

``--availability-zone`` (string)


  The EC2 Availability Zone (AZ) in which you want Amazon Redshift to provision the cluster. For example, if you have several EC2 instances running in a specific Availability Zone, then you might want the cluster to be provisioned in the same zone in order to decrease network latency. 

   

  Default: A random, system-chosen Availability Zone in the region that is specified by the endpoint. 

   

  Example: ``us-east-1d``  

   

  Constraint: The specified Availability Zone must be in the same region as the current endpoint. 

  

``--preferred-maintenance-window`` (string)


  The weekly time range (in UTC) during which automated cluster maintenance can occur. 

   

  Format: ``ddd:hh24:mi-ddd:hh24:mi``  

   

  Default: A 30-minute window selected at random from an 8-hour block of time per region, occurring on a random day of the week. For more information about the time blocks for each region, see `Maintenance Windows`_ in Amazon Redshift Cluster Management Guide.

   

  Valid Days: Mon | Tue | Wed | Thu | Fri | Sat | Sun

   

  Constraints: Minimum 30-minute window.

  

``--cluster-parameter-group-name`` (string)


  The name of the parameter group to be associated with this cluster. 

   

  Default: The default Amazon Redshift cluster parameter group. For information about the default parameter group, go to `Working with Amazon Redshift Parameter Groups`_ 

   

  Constraints: 

   

   
  * Must be 1 to 255 alphanumeric characters or hyphens.
   
  * First character must be a letter.
   
  * Cannot end with a hyphen or contain two consecutive hyphens.
   

  

``--automated-snapshot-retention-period`` (integer)


  The number of days that automated snapshots are retained. If the value is 0, automated snapshots are disabled. Even if automated snapshots are disabled, you can still create manual snapshots when you want with  create-cluster-snapshot . 

   

  Default: ``1``  

   

  Constraints: Must be a value from 0 to 35.

  

``--port`` (integer)


  The port number on which the cluster accepts incoming connections. 

   

  The cluster is accessible only via the JDBC and ODBC connection strings. Part of the connection string requires the port on which the cluster will listen for incoming connections.

   

  Default: ``5439``  

   

  Valid Values: ``1150-65535``  

  

``--cluster-version`` (string)


  The version of the Amazon Redshift engine software that you want to deploy on the cluster. 

   

  The version selected runs on all the nodes in the cluster. 

   

  Constraints: Only version 1.0 is currently available.

   

  Example: ``1.0`` 

  

``--allow-version-upgrade`` | ``--no-allow-version-upgrade`` (boolean)


  If ``true`` , major version upgrades can be applied during the maintenance window to the Amazon Redshift engine that is running on the cluster.

   

  When a new major version of the Amazon Redshift engine is released, you can request that the service automatically apply upgrades during the maintenance window to the Amazon Redshift engine that is running on your cluster. 

   

  Default: ``true`` 

  

``--number-of-nodes`` (integer)


  The number of compute nodes in the cluster. This parameter is required when the **ClusterType** parameter is specified as ``multi-node`` . 

   

  For information about determining how many nodes you need, go to `Working with Clusters`_ in the *Amazon Redshift Cluster Management Guide* . 

   

  If you don't specify this parameter, you get a single-node cluster. When requesting a multi-node cluster, you must specify the number of nodes that you want in the cluster.

   

  Default: ``1`` 

   

  Constraints: Value must be at least 1 and no more than 100.

  

``--publicly-accessible`` | ``--no-publicly-accessible`` (boolean)


  If ``true`` , the cluster can be accessed from a public network. 

  

``--encrypted`` | ``--no-encrypted`` (boolean)


  If ``true`` , the data in the cluster is encrypted at rest. 

   

  Default: false

  

``--hsm-client-certificate-identifier`` (string)


  Specifies the name of the HSM client certificate the Amazon Redshift cluster uses to retrieve the data encryption keys stored in an HSM.

  

``--hsm-configuration-identifier`` (string)


  Specifies the name of the HSM configuration that contains the information the Amazon Redshift cluster can use to retrieve and store keys in an HSM.

  

``--elastic-ip`` (string)


  The Elastic IP (EIP) address for the cluster.

   

  Constraints: The cluster must be provisioned in EC2-VPC and publicly-accessible through an Internet gateway. For more information about provisioning clusters in EC2-VPC, go to `Supported Platforms to Launch Your Cluster`_ in the Amazon Redshift Cluster Management Guide.

  

``--tags`` (list)


  A list of tag instances.

  



Shorthand Syntax::

    Key=string,Value=string ...




JSON Syntax::

  [
    {
      "Key": "string",
      "Value": "string"
    }
    ...
  ]



``--kms-key-id`` (string)


  The AWS Key Management Service (KMS) key ID of the encryption key that you want to use to encrypt data in the cluster.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

Create a Cluster with Minimal Parameters
----------------------------------------

This example creates a cluster with the minimal set of parameters. By default, the output is in JSON format.

Command::

   aws redshift create-cluster --node-type dw.hs1.xlarge --number-of-nodes 2 --master-username adminuser --master-user-password TopSecret1 --cluster-identifier mycluster

Result::

    {
       "Cluster": {
          "NodeType": "dw.hs1.xlarge",
          "ClusterVersion": "1.0",
          "PubliclyAccessible": "true",
          "MasterUsername": "adminuser",
          "ClusterParameterGroups": [
             {
                "ParameterApplyStatus": "in-sync",
                "ParameterGroupName": "default.redshift-1.0"
             } ],
          "ClusterSecurityGroups": [
             {
                "Status": "active",
                "ClusterSecurityGroupName": "default"
             } ],
          "AllowVersionUpgrade": true,
          "VpcSecurityGroups": \[],
          "PreferredMaintenanceWindow": "sat:03:30-sat:04:00",
          "AutomatedSnapshotRetentionPeriod": 1,
          "ClusterStatus": "creating",
          "ClusterIdentifier": "mycluster",
          "DBName": "dev",
          "NumberOfNodes": 2,
          "PendingModifiedValues": {
             "MasterUserPassword": "\****"
          }
       },
       "ResponseMetadata": {
          "RequestId": "7cf4bcfc-64dd-11e2-bea9-49e0ce183f07"
       }
    }




======
Output
======

Cluster -> (structure)

  

  Describes a cluster.

  

  ClusterIdentifier -> (string)

    

    The unique identifier of the cluster. 

    

    

  NodeType -> (string)

    

    The node type for the nodes in the cluster. 

    

    

  ClusterStatus -> (string)

    

    The current state of this cluster. Possible values include ``available`` , ``creating`` , ``deleting`` , ``rebooting`` , ``renaming`` , and ``resizing`` . 

    

    

  ModifyStatus -> (string)

    

    The status of a modify operation, if any, initiated for the cluster.

    

    

  MasterUsername -> (string)

    

    The master user name for the cluster. This name is used to connect to the database that is specified in **DBName** . 

    

    

  DBName -> (string)

    

    The name of the initial database that was created when the cluster was created. This same name is returned for the life of the cluster. If an initial database was not specified, a database named "dev" was created by default. 

    

    

  Endpoint -> (structure)

    

    The connection endpoint. 

    

    Address -> (string)

      

      The DNS address of the Cluster. 

      

      

    Port -> (integer)

      

      The port that the database engine is listening on. 

      

      

    

  ClusterCreateTime -> (timestamp)

    

    The date and time that the cluster was created. 

    

    

  AutomatedSnapshotRetentionPeriod -> (integer)

    

    The number of days that automatic cluster snapshots are retained. 

    

    

  ClusterSecurityGroups -> (list)

    

    A list of cluster security group that are associated with the cluster. Each security group is represented by an element that contains ``ClusterSecurityGroup.Name`` and ``ClusterSecurityGroup.Status`` subelements. 

     

    Cluster security groups are used when the cluster is not created in a VPC. Clusters that are created in a VPC use VPC security groups, which are listed by the **VpcSecurityGroups** parameter. 

    

    (structure)

      

      Describes a security group.

      

      ClusterSecurityGroupName -> (string)

        

        The name of the cluster security group. 

        

        

      Status -> (string)

        

        The status of the cluster security group. 

        

        

      

    

  VpcSecurityGroups -> (list)

    

    A list of Virtual Private Cloud (VPC) security groups that are associated with the cluster. This parameter is returned only if the cluster is in a VPC. 

    

    (structure)

      

      Describes the members of a VPC security group.

      

      VpcSecurityGroupId -> (string)

        

        

      Status -> (string)

        

        

      

    

  ClusterParameterGroups -> (list)

    

    The list of cluster parameter groups that are associated with this cluster. Each parameter group in the list is returned with its status.

    

    (structure)

      

      Describes the status of a parameter group. 

      

      ParameterGroupName -> (string)

        

        The name of the cluster parameter group. 

        

        

      ParameterApplyStatus -> (string)

        

        The status of parameter updates. 

        

        

      ClusterParameterStatusList -> (list)

        

        The list of parameter statuses.

         

        For more information about parameters and parameter groups, go to `Amazon Redshift Parameter Groups`_ in the *Amazon Redshift Cluster Management Guide* . 

        

        (structure)

          

          Describes the status of a parameter group.

          

          ParameterName -> (string)

            

            The name of the parameter.

            

            

          ParameterApplyStatus -> (string)

            

            The status of the parameter that indicates whether the parameter is in sync with the database, waiting for a cluster reboot, or encountered an error when being applied.

             

            The following are possible statuses and descriptions.

             
            * ``in-sync`` : The parameter value is in sync with the database.
             
            * ``pending-reboot`` : The parameter value will be applied after the cluster reboots.
             
            * ``applying`` : The parameter value is being applied to the database.
             
            * ``invalid-parameter`` : Cannot apply the parameter value because it has an invalid value or syntax.
             
            * ``apply-deferred`` : The parameter contains static property changes. The changes are deferred until the cluster reboots.
             
            * ``apply-error`` : Cannot connect to the cluster. The parameter change will be applied after the cluster reboots.
             
            * ``unknown-error`` : Cannot apply the parameter change right now. The change will be applied after the cluster reboots.
             

             

            

            

          ParameterApplyErrorDescription -> (string)

            

            The error that prevented the parameter from being applied to the database.

            

            

          

        

      

    

  ClusterSubnetGroupName -> (string)

    

    The name of the subnet group that is associated with the cluster. This parameter is valid only when the cluster is in a VPC. 

    

    

  VpcId -> (string)

    

    The identifier of the VPC the cluster is in, if the cluster is in a VPC. 

    

    

  AvailabilityZone -> (string)

    

    The name of the Availability Zone in which the cluster is located. 

    

    

  PreferredMaintenanceWindow -> (string)

    

    The weekly time range (in UTC) during which system maintenance can occur. 

    

    

  PendingModifiedValues -> (structure)

    

    If present, changes to the cluster are pending. Specific pending changes are identified by subelements. 

    

    MasterUserPassword -> (string)

      

      The pending or in-progress change of the master user password for the cluster. 

      

      

    NodeType -> (string)

      

      The pending or in-progress change of the cluster's node type. 

      

      

    NumberOfNodes -> (integer)

      

      The pending or in-progress change of the number of nodes in the cluster. 

      

      

    ClusterType -> (string)

      

      The pending or in-progress change of the cluster type. 

      

      

    ClusterVersion -> (string)

      

      The pending or in-progress change of the service version. 

      

      

    AutomatedSnapshotRetentionPeriod -> (integer)

      

      The pending or in-progress change of the automated snapshot retention period. 

      

      

    ClusterIdentifier -> (string)

      

      The pending or in-progress change of the new identifier for the cluster.

      

      

    

  ClusterVersion -> (string)

    

    The version ID of the Amazon Redshift engine that is running on the cluster. 

    

    

  AllowVersionUpgrade -> (boolean)

    

    If ``true`` , major version upgrades will be applied automatically to the cluster during the maintenance window. 

    

    

  NumberOfNodes -> (integer)

    

    The number of compute nodes in the cluster. 

    

    

  PubliclyAccessible -> (boolean)

    

    If ``true`` , the cluster can be accessed from a public network.

    

    

  Encrypted -> (boolean)

    

    If ``true`` , data in the cluster is encrypted at rest.

    

    

  RestoreStatus -> (structure)

    

    Describes the status of a cluster restore action. Returns null if the cluster was not created by restoring a snapshot. 

    

    Status -> (string)

      

      The status of the restore action. Returns starting, restoring, completed, or failed. 

      

      

    CurrentRestoreRateInMegaBytesPerSecond -> (double)

      

      The number of megabytes per second being transferred from the backup storage. Returns the average rate for a completed backup. 

      

      

    SnapshotSizeInMegaBytes -> (long)

      

      The size of the set of snapshot data used to restore the cluster. 

      

      

    ProgressInMegaBytes -> (long)

      

      The number of megabytes that have been transferred from snapshot storage. 

      

      

    ElapsedTimeInSeconds -> (long)

      

      The amount of time an in-progress restore has been running, or the amount of time it took a completed restore to finish. 

      

      

    EstimatedTimeToCompletionInSeconds -> (long)

      

      The estimate of the time remaining before the restore will complete. Returns 0 for a completed restore. 

      

      

    

  HsmStatus -> (structure)

    

    Reports whether the Amazon Redshift cluster has finished applying any HSM settings changes specified in a modify cluster command.

     

    Values: active, applying

    

    HsmClientCertificateIdentifier -> (string)

      

      Specifies the name of the HSM client certificate the Amazon Redshift cluster uses to retrieve the data encryption keys stored in an HSM.

      

      

    HsmConfigurationIdentifier -> (string)

      

      Specifies the name of the HSM configuration that contains the information the Amazon Redshift cluster can use to retrieve and store keys in an HSM.

      

      

    Status -> (string)

      

      Reports whether the Amazon Redshift cluster has finished applying any HSM settings changes specified in a modify cluster command.

       

      Values: active, applying

      

      

    

  ClusterSnapshotCopyStatus -> (structure)

    

    Returns the destination region and retention period that are configured for cross-region snapshot copy. 

    

    DestinationRegion -> (string)

      

      The destination region that snapshots are automatically copied to when cross-region snapshot copy is enabled.

      

      

    RetentionPeriod -> (long)

      

      The number of days that automated snapshots are retained in the destination region after they are copied from a source region.

      

      

    SnapshotCopyGrantName -> (string)

      

      The name of the snapshot copy grant.

      

      

    

  ClusterPublicKey -> (string)

    

    The public key for the cluster.

    

    

  ClusterNodes -> (list)

    

    The nodes in a cluster.

    

    (structure)

      

      The identifier of a node in a cluster.

      

      NodeRole -> (string)

        

        Whether the node is a leader node or a compute node.

        

        

      PrivateIPAddress -> (string)

        

        The private IP address of a node within a cluster.

        

        

      PublicIPAddress -> (string)

        

        The public IP address of a node within a cluster.

        

        

      

    

  ElasticIpStatus -> (structure)

    

    Describes the status of the elastic IP (EIP) address.

    

    ElasticIp -> (string)

      

      The elastic IP (EIP) address for the cluster.

      

      

    Status -> (string)

      

      Describes the status of the elastic IP (EIP) address.

      

      

    

  ClusterRevisionNumber -> (string)

    

    The specific revision number of the database in the cluster.

    

    

  Tags -> (list)

    

    The list of tags for the cluster.

    

    (structure)

      

      A tag consisting of a name/value pair for a resource.

      

      Key -> (string)

        

        The key, or name, for the resource tag.

        

        

      Value -> (string)

        

        The value for the resource tag.

        

        

      

    

  KmsKeyId -> (string)

    

    The AWS Key Management Service (KMS) key ID of the encryption key used to encrypt data in the cluster.

    

    

  



.. _Working with Clusters: http://docs.aws.amazon.com/redshift/latest/mgmt/working-with-clusters.html#how-many-nodes
.. _Create a Database: http://docs.aws.amazon.com/redshift/latest/dg/t_creating_database.html
.. _Amazon Redshift Clusters: http://docs.aws.amazon.com/redshift/latest/mgmt/working-with-clusters.html
.. _Amazon Redshift Parameter Groups: http://docs.aws.amazon.com/redshift/latest/mgmt/working-with-parameter-groups.html
.. _Working with Amazon Redshift Parameter Groups: http://docs.aws.amazon.com/redshift/latest/mgmt/working-with-parameter-groups.html
.. _Reserved Words: http://docs.aws.amazon.com/redshift/latest/dg/r_pg_keywords.html
.. _Maintenance Windows: http://docs.aws.amazon.com/redshift/latest/mgmt/working-with-clusters.html#rs-maintenance-windows
.. _Supported Platforms to Launch Your Cluster: http://docs.aws.amazon.com/redshift/latest/mgmt/working-with-clusters.html#cluster-platforms
