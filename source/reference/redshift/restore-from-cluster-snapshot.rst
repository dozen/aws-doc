[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift restore-from-cluster-snapshot:


*****************************
restore-from-cluster-snapshot
*****************************



===========
Description
===========



Creates a new cluster from a snapshot. By default, Amazon Redshift creates the resulting cluster with the same configuration as the original cluster from which the snapshot was created, except that the new cluster is created with the default cluster security and parameter groups. After Amazon Redshift creates the cluster, you can use the  modify-cluster API to associate a different security group and different parameter group with the restored cluster. If you are using a DS node type, you can also choose to change to another DS node type of the same size during restore.

 

If you restore a cluster into a VPC, you must provide a cluster subnet group where you want the cluster restored.

 

For more information about working with snapshots, go to `Amazon Redshift Snapshots <http://docs.aws.amazon.com/redshift/latest/mgmt/working-with-snapshots.html>`_ in the *Amazon Redshift Cluster Management Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/redshift-2012-12-01/RestoreFromClusterSnapshot>`_


========
Synopsis
========

::

    restore-from-cluster-snapshot
  --cluster-identifier <value>
  --snapshot-identifier <value>
  [--snapshot-cluster-identifier <value>]
  [--port <value>]
  [--availability-zone <value>]
  [--allow-version-upgrade | --no-allow-version-upgrade]
  [--cluster-subnet-group-name <value>]
  [--publicly-accessible | --no-publicly-accessible]
  [--owner-account <value>]
  [--hsm-client-certificate-identifier <value>]
  [--hsm-configuration-identifier <value>]
  [--elastic-ip <value>]
  [--cluster-parameter-group-name <value>]
  [--cluster-security-groups <value>]
  [--vpc-security-group-ids <value>]
  [--preferred-maintenance-window <value>]
  [--automated-snapshot-retention-period <value>]
  [--kms-key-id <value>]
  [--node-type <value>]
  [--enhanced-vpc-routing | --no-enhanced-vpc-routing]
  [--additional-info <value>]
  [--iam-roles <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cluster-identifier`` (string)


  The identifier of the cluster that will be created from restoring the snapshot.

   

  Constraints:

   

   
  * Must contain from 1 to 63 alphanumeric characters or hyphens. 
   
  * Alphabetic characters must be lowercase. 
   
  * First character must be a letter. 
   
  * Cannot end with a hyphen or contain two consecutive hyphens. 
   
  * Must be unique for all clusters within an AWS account. 
   

  

``--snapshot-identifier`` (string)


  The name of the snapshot from which to create the new cluster. This parameter isn't case sensitive.

   

  Example: ``my-snapshot-id``  

  

``--snapshot-cluster-identifier`` (string)


  The name of the cluster the source snapshot was created from. This parameter is required if your IAM user has a policy containing a snapshot resource element that specifies anything other than * for the cluster name.

  

``--port`` (integer)


  The port number on which the cluster accepts connections.

   

  Default: The same port as the original cluster.

   

  Constraints: Must be between ``1115`` and ``65535`` .

  

``--availability-zone`` (string)


  The Amazon EC2 Availability Zone in which to restore the cluster.

   

  Default: A random, system-chosen Availability Zone.

   

  Example: ``us-east-1a``  

  

``--allow-version-upgrade`` | ``--no-allow-version-upgrade`` (boolean)


  If ``true`` , major version upgrades can be applied during the maintenance window to the Amazon Redshift engine that is running on the cluster. 

   

  Default: ``true``  

  

``--cluster-subnet-group-name`` (string)


  The name of the subnet group where you want to cluster restored.

   

  A snapshot of cluster in VPC can be restored only in VPC. Therefore, you must provide subnet group name where you want the cluster restored.

  

``--publicly-accessible`` | ``--no-publicly-accessible`` (boolean)


  If ``true`` , the cluster can be accessed from a public network. 

  

``--owner-account`` (string)


  The AWS customer account used to create or copy the snapshot. Required if you are restoring a snapshot you do not own, optional if you own the snapshot.

  

``--hsm-client-certificate-identifier`` (string)


  Specifies the name of the HSM client certificate the Amazon Redshift cluster uses to retrieve the data encryption keys stored in an HSM.

  

``--hsm-configuration-identifier`` (string)


  Specifies the name of the HSM configuration that contains the information the Amazon Redshift cluster can use to retrieve and store keys in an HSM.

  

``--elastic-ip`` (string)


  The elastic IP (EIP) address for the cluster.

  

``--cluster-parameter-group-name`` (string)


  The name of the parameter group to be associated with this cluster.

   

  Default: The default Amazon Redshift cluster parameter group. For information about the default parameter group, go to `Working with Amazon Redshift Parameter Groups <http://docs.aws.amazon.com/redshift/latest/mgmt/working-with-parameter-groups.html>`_ .

   

  Constraints:

   

   
  * Must be 1 to 255 alphanumeric characters or hyphens. 
   
  * First character must be a letter. 
   
  * Cannot end with a hyphen or contain two consecutive hyphens. 
   

  

``--cluster-security-groups`` (list)


  A list of security groups to be associated with this cluster.

   

  Default: The default cluster security group for Amazon Redshift.

   

  Cluster security groups only apply to clusters outside of VPCs.

  



Syntax::

  "string" "string" ...



``--vpc-security-group-ids`` (list)


  A list of Virtual Private Cloud (VPC) security groups to be associated with the cluster.

   

  Default: The default VPC security group is associated with the cluster.

   

  VPC security groups only apply to clusters in VPCs.

  



Syntax::

  "string" "string" ...



``--preferred-maintenance-window`` (string)


  The weekly time range (in UTC) during which automated cluster maintenance can occur.

   

  Format: ``ddd:hh24:mi-ddd:hh24:mi``  

   

  Default: The value selected for the cluster from which the snapshot was taken. For more information about the time blocks for each region, see `Maintenance Windows <http://docs.aws.amazon.com/redshift/latest/mgmt/working-with-clusters.html#rs-maintenance-windows>`_ in Amazon Redshift Cluster Management Guide. 

   

  Valid Days: Mon | Tue | Wed | Thu | Fri | Sat | Sun

   

  Constraints: Minimum 30-minute window.

  

``--automated-snapshot-retention-period`` (integer)


  The number of days that automated snapshots are retained. If the value is 0, automated snapshots are disabled. Even if automated snapshots are disabled, you can still create manual snapshots when you want with  create-cluster-snapshot . 

   

  Default: The value selected for the cluster from which the snapshot was taken.

   

  Constraints: Must be a value from 0 to 35.

  

``--kms-key-id`` (string)


  The AWS Key Management Service (KMS) key ID of the encryption key that you want to use to encrypt data in the cluster that you restore from a shared snapshot.

  

``--node-type`` (string)


  The node type that the restored cluster will be provisioned with.

   

  Default: The node type of the cluster from which the snapshot was taken. You can modify this if you are using any DS node type. In that case, you can choose to restore into another DS node type of the same size. For example, you can restore ds1.8xlarge into ds2.8xlarge, or ds2.xlarge into ds1.xlarge. If you have a DC instance type, you must restore into that same instance type and size. In other words, you can only restore a dc1.large instance type into another dc1.large instance type. For more information about node types, see `About Clusters and Nodes <http://docs.aws.amazon.com/redshift/latest/mgmt/working-with-clusters.html#rs-about-clusters-and-nodes>`_ in the *Amazon Redshift Cluster Management Guide*  

  

``--enhanced-vpc-routing`` | ``--no-enhanced-vpc-routing`` (boolean)


  An option that specifies whether to create the cluster with enhanced VPC routing enabled. To create a cluster that uses enhanced VPC routing, the cluster must be in a VPC. For more information, see `Enhanced VPC Routing <http://docs.aws.amazon.com/redshift/latest/mgmt/enhanced-vpc-routing.html>`_ in the Amazon Redshift Cluster Management Guide.

   

  If this option is ``true`` , enhanced VPC routing is enabled. 

   

  Default: false

  

``--additional-info`` (string)


  Reserved.

  

``--iam-roles`` (list)


  A list of AWS Identity and Access Management (IAM) roles that can be used by the cluster to access other AWS services. You must supply the IAM roles in their Amazon Resource Name (ARN) format. You can supply up to 10 IAM roles in a single request.

   

  A cluster can have up to 10 IAM roles associated at any time.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

Restore a Cluster From a Snapshot
---------------------------------

This example restores a cluster from a snapshot.

Command::

   aws redshift restore-from-cluster-snapshot --cluster-identifier mycluster-clone --snapshot-identifier my-snapshot-id

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
             }
          ],
          "ClusterSecurityGroups": [
             {
             "Status": "active",
             "ClusterSecurityGroupName": "default"
             }
          ],
          "AllowVersionUpgrade": true,
          "VpcSecurityGroups": \[],
          "PreferredMaintenanceWindow": "sun:23:15-mon:03:15",
          "AutomatedSnapshotRetentionPeriod": 1,
          "ClusterStatus": "creating",
          "ClusterIdentifier": "mycluster-clone",
          "DBName": "dev",
          "NumberOfNodes": 2,
          "PendingModifiedValues": {}
       },
       "ResponseMetadata": {
          "RequestId": "77fd512b-64e3-11e2-8f5b-e90bd6c77476"
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

    

    The current state of the cluster. Possible values are the following:

     

     
    * ``available``   
     
    * ``creating``   
     
    * ``deleting``   
     
    * ``final-snapshot``   
     
    * ``hardware-failure``   
     
    * ``incompatible-hsm``   
     
    * ``incompatible-network``   
     
    * ``incompatible-parameters``   
     
    * ``incompatible-restore``   
     
    * ``modifying``   
     
    * ``rebooting``   
     
    * ``renaming``   
     
    * ``resizing``   
     
    * ``rotating-keys``   
     
    * ``storage-full``   
     
    * ``updating-hsm``   
     

    

    

  ModifyStatus -> (string)

    

    The status of a modify operation, if any, initiated for the cluster.

    

    

  MasterUsername -> (string)

    

    The master user name for the cluster. This name is used to connect to the database that is specified in the **DBName** parameter. 

    

    

  DBName -> (string)

    

    The name of the initial database that was created when the cluster was created. This same name is returned for the life of the cluster. If an initial database was not specified, a database named ``dev`` dev was created by default. 

    

    

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

     

    Cluster security groups are used when the cluster is not created in an Amazon Virtual Private Cloud (VPC). Clusters that are created in a VPC use VPC security groups, which are listed by the **VpcSecurityGroups** parameter. 

    

    (structure)

      

      Describes a cluster security group.

      

      ClusterSecurityGroupName -> (string)

        

        The name of the cluster security group.

        

        

      Status -> (string)

        

        The status of the cluster security group.

        

        

      

    

  VpcSecurityGroups -> (list)

    

    A list of Amazon Virtual Private Cloud (Amazon VPC) security groups that are associated with the cluster. This parameter is returned only if the cluster is in a VPC.

    

    (structure)

      

      Describes the members of a VPC security group.

      

      VpcSecurityGroupId -> (string)

        

        The identifier of the VPC security group.

        

        

      Status -> (string)

        

        The status of the VPC security group.

        

        

      

    

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

         

        For more information about parameters and parameter groups, go to `Amazon Redshift Parameter Groups <http://docs.aws.amazon.com/redshift/latest/mgmt/working-with-parameter-groups.html>`_ in the *Amazon Redshift Cluster Management Guide* .

        

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

    

    The weekly time range, in Universal Coordinated Time (UTC), during which system maintenance can occur.

    

    

  PendingModifiedValues -> (structure)

    

    A value that, if present, indicates that changes to the cluster are pending. Specific pending changes are identified by subelements.

    

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

      

      

    PubliclyAccessible -> (boolean)

      

      The pending or in-progress change of the ability to connect to the cluster from the public network.

      

      

    EnhancedVpcRouting -> (boolean)

      

      An option that specifies whether to create the cluster with enhanced VPC routing enabled. To create a cluster that uses enhanced VPC routing, the cluster must be in a VPC. For more information, see `Enhanced VPC Routing <http://docs.aws.amazon.com/redshift/latest/mgmt/enhanced-vpc-routing.html>`_ in the Amazon Redshift Cluster Management Guide.

       

      If this option is ``true`` , enhanced VPC routing is enabled. 

       

      Default: false

      

      

    

  ClusterVersion -> (string)

    

    The version ID of the Amazon Redshift engine that is running on the cluster.

    

    

  AllowVersionUpgrade -> (boolean)

    

    A Boolean value that, if ``true`` , indicates that major version upgrades will be applied automatically to the cluster during the maintenance window. 

    

    

  NumberOfNodes -> (integer)

    

    The number of compute nodes in the cluster.

    

    

  PubliclyAccessible -> (boolean)

    

    A Boolean value that, if ``true`` , indicates that the cluster can be accessed from a public network.

    

    

  Encrypted -> (boolean)

    

    A Boolean value that, if ``true`` , indicates that data in the cluster is encrypted at rest.

    

    

  RestoreStatus -> (structure)

    

    A value that describes the status of a cluster restore action. This parameter returns null if the cluster was not created by restoring a snapshot.

    

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

    

    A value that reports whether the Amazon Redshift cluster has finished applying any hardware security module (HSM) settings changes specified in a modify cluster command.

     

    Values: active, applying

    

    HsmClientCertificateIdentifier -> (string)

      

      Specifies the name of the HSM client certificate the Amazon Redshift cluster uses to retrieve the data encryption keys stored in an HSM.

      

      

    HsmConfigurationIdentifier -> (string)

      

      Specifies the name of the HSM configuration that contains the information the Amazon Redshift cluster can use to retrieve and store keys in an HSM.

      

      

    Status -> (string)

      

      Reports whether the Amazon Redshift cluster has finished applying any HSM settings changes specified in a modify cluster command.

       

      Values: active, applying

      

      

    

  ClusterSnapshotCopyStatus -> (structure)

    

    A value that returns the destination region and retention period that are configured for cross-region snapshot copy.

    

    DestinationRegion -> (string)

      

      The destination region that snapshots are automatically copied to when cross-region snapshot copy is enabled.

      

      

    RetentionPeriod -> (long)

      

      The number of days that automated snapshots are retained in the destination region after they are copied from a source region.

      

      

    SnapshotCopyGrantName -> (string)

      

      The name of the snapshot copy grant.

      

      

    

  ClusterPublicKey -> (string)

    

    The public key for the cluster.

    

    

  ClusterNodes -> (list)

    

    The nodes in the cluster.

    

    (structure)

      

      The identifier of a node in a cluster.

      

      NodeRole -> (string)

        

        Whether the node is a leader node or a compute node.

        

        

      PrivateIPAddress -> (string)

        

        The private IP address of a node within a cluster.

        

        

      PublicIPAddress -> (string)

        

        The public IP address of a node within a cluster.

        

        

      

    

  ElasticIpStatus -> (structure)

    

    The status of the elastic IP (EIP) address.

    

    ElasticIp -> (string)

      

      The elastic IP (EIP) address for the cluster.

      

      

    Status -> (string)

      

      The status of the elastic IP (EIP) address.

      

      

    

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

    

    The AWS Key Management Service (AWS KMS) key ID of the encryption key used to encrypt data in the cluster.

    

    

  EnhancedVpcRouting -> (boolean)

    

    An option that specifies whether to create the cluster with enhanced VPC routing enabled. To create a cluster that uses enhanced VPC routing, the cluster must be in a VPC. For more information, see `Enhanced VPC Routing <http://docs.aws.amazon.com/redshift/latest/mgmt/enhanced-vpc-routing.html>`_ in the Amazon Redshift Cluster Management Guide.

     

    If this option is ``true`` , enhanced VPC routing is enabled. 

     

    Default: false

    

    

  IamRoles -> (list)

    

    A list of AWS Identity and Access Management (IAM) roles that can be used by the cluster to access other AWS services.

    

    (structure)

      

      An AWS Identity and Access Management (IAM) role that can be used by the associated Amazon Redshift cluster to access other AWS services.

      

      IamRoleArn -> (string)

        

        The Amazon Resource Name (ARN) of the IAM role, for example, ``arn:aws:iam::123456789012:role/RedshiftCopyUnload`` . 

        

        

      ApplyStatus -> (string)

        

        A value that describes the status of the IAM role's association with an Amazon Redshift cluster.

         

        The following are possible statuses and descriptions.

         

         
        * ``in-sync`` : The role is available for use by the cluster. 
         
        * ``adding`` : The role is in the process of being associated with the cluster. 
         
        * ``removing`` : The role is in the process of being disassociated with the cluster. 
         

        

        

      

    

  

