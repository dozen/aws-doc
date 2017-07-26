[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift enable-snapshot-copy:


********************
enable-snapshot-copy
********************



===========
Description
===========



Enables the automatic copy of snapshots from one region to another region for a specified cluster.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/redshift-2012-12-01/EnableSnapshotCopy>`_


========
Synopsis
========

::

    enable-snapshot-copy
  --cluster-identifier <value>
  --destination-region <value>
  [--retention-period <value>]
  [--snapshot-copy-grant-name <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cluster-identifier`` (string)


  The unique identifier of the source cluster to copy snapshots from.

   

  Constraints: Must be the valid name of an existing cluster that does not already have cross-region snapshot copy enabled.

  

``--destination-region`` (string)


  The destination region that you want to copy snapshots to.

   

  Constraints: Must be the name of a valid region. For more information, see `Regions and Endpoints <http://docs.aws.amazon.com/general/latest/gr/rande.html#redshift_region>`_ in the Amazon Web Services General Reference. 

  

``--retention-period`` (integer)


  The number of days to retain automated snapshots in the destination region after they are copied from the source region.

   

  Default: 7.

   

  Constraints: Must be at least 1 and no more than 35.

  

``--snapshot-copy-grant-name`` (string)


  The name of the snapshot copy grant to use when snapshots of an AWS KMS-encrypted cluster are copied to the destination region.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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
         

        

        

      

    

  

