[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift modify-cluster:


**************
modify-cluster
**************



===========
Description
===========



Modifies the settings for a cluster. For example, you can add another security or parameter group, update the preferred maintenance window, or change the master user password. Resetting a cluster password or modifying the security groups associated with a cluster do not need a reboot. However, modifying a parameter group requires a reboot for parameters to take effect. For more information about managing clusters, go to `Amazon Redshift Clusters`_ in the *Amazon Redshift Cluster Management Guide* . 

 

You can also change node type and the number of nodes to scale up or down the cluster. When resizing a cluster, you must specify both the number of nodes and the node type even if one of the parameters does not change.



========
Synopsis
========

::

    modify-cluster
  --cluster-identifier <value>
  [--cluster-type <value>]
  [--node-type <value>]
  [--number-of-nodes <value>]
  [--cluster-security-groups <value>]
  [--vpc-security-group-ids <value>]
  [--master-user-password <value>]
  [--cluster-parameter-group-name <value>]
  [--automated-snapshot-retention-period <value>]
  [--preferred-maintenance-window <value>]
  [--cluster-version <value>]
  [--allow-version-upgrade | --no-allow-version-upgrade]
  [--hsm-client-certificate-identifier <value>]
  [--hsm-configuration-identifier <value>]
  [--new-cluster-identifier <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cluster-identifier`` (string)


  The unique identifier of the cluster to be modified. 

   

  Example: ``examplecluster`` 

  

``--cluster-type`` (string)


  The new cluster type. 

   

  When you submit your cluster resize request, your existing cluster goes into a read-only mode. After Amazon Redshift provisions a new cluster based on your resize requirements, there will be outage for a period while the old cluster is deleted and your connection is switched to the new cluster. You can use  describe-resize to track the progress of the resize request. 

   

  Valid Values: ``multi-node | single-node`` 

  

``--node-type`` (string)


  The new node type of the cluster. If you specify a new node type, you must also specify the number of nodes parameter. 

   

  When you submit your request to resize a cluster, Amazon Redshift sets access permissions for the cluster to read-only. After Amazon Redshift provisions a new cluster according to your resize requirements, there will be a temporary outage while the old cluster is deleted and your connection is switched to the new cluster. When the new connection is complete, the original access permissions for the cluster are restored. You can use  describe-resize to track the progress of the resize request. 

   

  Valid Values: ``ds1.xlarge`` | ``ds1.8xlarge`` | ``ds2.xlarge`` | ``ds2.8xlarge`` | ``dc1.large`` | ``dc1.8xlarge`` .

  

``--number-of-nodes`` (integer)


  The new number of nodes of the cluster. If you specify a new number of nodes, you must also specify the node type parameter. 

   

  When you submit your request to resize a cluster, Amazon Redshift sets access permissions for the cluster to read-only. After Amazon Redshift provisions a new cluster according to your resize requirements, there will be a temporary outage while the old cluster is deleted and your connection is switched to the new cluster. When the new connection is complete, the original access permissions for the cluster are restored. You can use  describe-resize to track the progress of the resize request. 

   

  Valid Values: Integer greater than ``0`` .

  

``--cluster-security-groups`` (list)


  A list of cluster security groups to be authorized on this cluster. This change is asynchronously applied as soon as possible. 

   

  Security groups currently associated with the cluster, and not in the list of groups to apply, will be revoked from the cluster.

   

  Constraints:

   

   
  * Must be 1 to 255 alphanumeric characters or hyphens
   
  * First character must be a letter
   
  * Cannot end with a hyphen or contain two consecutive hyphens
   

  



Syntax::

  "string" "string" ...



``--vpc-security-group-ids`` (list)


  A list of virtual private cloud (VPC) security groups to be associated with the cluster. 

  



Syntax::

  "string" "string" ...



``--master-user-password`` (string)


  The new password for the cluster master user. This change is asynchronously applied as soon as possible. Between the time of the request and the completion of the request, the ``MasterUserPassword`` element exists in the ``PendingModifiedValues`` element of the operation response. 

  .. note::

    Operations never return the password, so this operation provides a way to regain access to the master user account for a cluster if the password is lost. 

   

   

  Default: Uses existing setting.

   

  Constraints: 

   

   
  * Must be between 8 and 64 characters in length.
   
  * Must contain at least one uppercase letter.
   
  * Must contain at least one lowercase letter.
   
  * Must contain one number.
   
  * Can be any printable ASCII character (ASCII code 33 to 126) except ' (single quote), " (double quote), \, /, @, or space.
   

  

``--cluster-parameter-group-name`` (string)


  The name of the cluster parameter group to apply to this cluster. This change is applied only after the cluster is rebooted. To reboot a cluster use  reboot-cluster . 

   

  Default: Uses existing setting.

   

  Constraints: The cluster parameter group must be in the same parameter group family that matches the cluster version.

  

``--automated-snapshot-retention-period`` (integer)


  The number of days that automated snapshots are retained. If the value is 0, automated snapshots are disabled. Even if automated snapshots are disabled, you can still create manual snapshots when you want with  create-cluster-snapshot . 

   

  If you decrease the automated snapshot retention period from its current value, existing automated snapshots that fall outside of the new retention period will be immediately deleted.

   

  Default: Uses existing setting.

   

  Constraints: Must be a value from 0 to 35.

  

``--preferred-maintenance-window`` (string)


  The weekly time range (in UTC) during which system maintenance can occur, if necessary. If system maintenance is necessary during the window, it may result in an outage. 

   

  This maintenance window change is made immediately. If the new maintenance window indicates the current time, there must be at least 120 minutes between the current time and end of the window in order to ensure that pending changes are applied. 

   

  Default: Uses existing setting.

   

  Format: ddd:hh24:mi-ddd:hh24:mi, for example ``wed:07:30-wed:08:00`` .

   

  Valid Days: Mon | Tue | Wed | Thu | Fri | Sat | Sun

   

  Constraints: Must be at least 30 minutes.

  

``--cluster-version`` (string)


  The new version number of the Amazon Redshift engine to upgrade to. 

   

  For major version upgrades, if a non-default cluster parameter group is currently in use, a new cluster parameter group in the cluster parameter group family for the new version must be specified. The new cluster parameter group can be the default for that cluster parameter group family. For more information about parameters and parameter groups, go to `Amazon Redshift Parameter Groups`_ in the *Amazon Redshift Cluster Management Guide* . 

   

  Example: ``1.0`` 

  

``--allow-version-upgrade`` | ``--no-allow-version-upgrade`` (boolean)


  If ``true`` , major version upgrades will be applied automatically to the cluster during the maintenance window. 

   

  Default: ``false`` 

  

``--hsm-client-certificate-identifier`` (string)


  Specifies the name of the HSM client certificate the Amazon Redshift cluster uses to retrieve the data encryption keys stored in an HSM.

  

``--hsm-configuration-identifier`` (string)


  Specifies the name of the HSM configuration that contains the information the Amazon Redshift cluster can use to retrieve and store keys in an HSM.

  

``--new-cluster-identifier`` (string)


  The new identifier for the cluster.

   

  Constraints:

   

   
  * Must contain from 1 to 63 alphanumeric characters or hyphens.
   
  * Alphabetic characters must be lowercase.
   
  * First character must be a letter.
   
  * Cannot end with a hyphen or contain two consecutive hyphens.
   
  * Must be unique for all clusters within an AWS account.
   

   

  Example: ``examplecluster`` 

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

Associate a Security Group with a Cluster
-----------------------------------------

This example shows how to associate a cluster security group with the specified cluster.

Command::

   aws redshift modify-cluster --cluster-identifier mycluster --cluster-security-groups mysecuritygroup


Modify the Maintenance Window for a Cluster
-------------------------------------------

This shows how to change the weekly preferred maintenance window for a cluster to be the minimum four hour window
starting Sundays at 11:15 PM, and ending Mondays at 3:15 AM.

Command::

   aws redshift modify-cluster --cluster-identifier mycluster --preferred-maintenance-window Sun:23:15-Mon:03:15

Change the Master Password for the Cluster
------------------------------------------

This example shows how to change the master password for a cluster.

Command::

   aws redshift modify-cluster --cluster-identifier mycluster --master-user-password A1b2c3d4




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

    

    

  



.. _Amazon Redshift Clusters: http://docs.aws.amazon.com/redshift/latest/mgmt/working-with-clusters.html
.. _Amazon Redshift Parameter Groups: http://docs.aws.amazon.com/redshift/latest/mgmt/working-with-parameter-groups.html
