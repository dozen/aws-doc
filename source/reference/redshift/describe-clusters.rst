[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift describe-clusters:


*****************
describe-clusters
*****************



===========
Description
===========



Returns properties of provisioned clusters including general cluster properties, cluster database properties, maintenance and backup properties, and security and access properties. This operation supports pagination. For more information about managing clusters, go to `Amazon Redshift Clusters`_ in the *Amazon Redshift Cluster Management Guide* . 

 

If you specify both tag keys and tag values in the same request, Amazon Redshift returns all clusters that match any combination of the specified keys and values. For example, if you have ``owner`` and ``environment`` for tag keys, and ``admin`` and ``test`` for tag values, all clusters that have any combination of those values are returned.

 

If both tag keys and values are omitted from the request, clusters are returned regardless of whether they have tag keys or values associated with them.



``describe-clusters`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``Clusters``


========
Synopsis
========

::

    describe-clusters
  [--cluster-identifier <value>]
  [--tag-keys <value>]
  [--tag-values <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cluster-identifier`` (string)


  The unique identifier of a cluster whose properties you are requesting. This parameter is case sensitive. 

   

  The default is that all clusters defined for an account are returned. 

  

``--tag-keys`` (list)


  A tag key or keys for which you want to return all matching clusters that are associated with the specified key or keys. For example, suppose that you have clusters that are tagged with keys called ``owner`` and ``environment`` . If you specify both of these tag keys in the request, Amazon Redshift returns a response with the clusters that have either or both of these tag keys associated with them.

  



Syntax::

  "string" "string" ...



``--tag-values`` (list)


  A tag value or values for which you want to return all matching clusters that are associated with the specified tag value or values. For example, suppose that you have clusters that are tagged with values called ``admin`` and ``test`` . If you specify both of these tag values in the request, Amazon Redshift returns a response with the clusters that have either or both of these tag values associated with them.

  



Syntax::

  "string" "string" ...



``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``NextToken`` from a previously truncated response.

   

``--page-size`` (integer)
 

  The size of each page.

   

  

  

``--max-items`` (integer)
 

  The total number of items to return. If the total number of items available is more than the value specified in max-items then a ``NextToken`` will be provided in the output that you can use to resume pagination. This ``NextToken`` response element should **not** be used directly outside of the AWS CLI.

   

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



========
Examples
========

Get a Description of All Clusters
---------------------------------

This example returns a description of all clusters for the account.  By default, the output is in JSON format.

Command::

   aws redshift describe-clusters

Result::

    {
       "Clusters": [
       {
          "NodeType": "dw.hs1.xlarge",
          "Endpoint": {
             "Port": 5439,
             "Address": "mycluster.coqoarplqhsn.us-east-1.redshift.amazonaws.com"
          },
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
          "AvailabilityZone": "us-east-1a",
          "ClusterCreateTime": "2013-01-22T21:59:29.559Z",
          "PreferredMaintenanceWindow": "sat:03:30-sat:04:00",
          "AutomatedSnapshotRetentionPeriod": 1,
          "ClusterStatus": "available",
          "ClusterIdentifier": "mycluster",
          "DBName": "dev",
          "NumberOfNodes": 2,
          "PendingModifiedValues": {}
       } ],
       "ResponseMetadata": {
          "RequestId": "65b71cac-64df-11e2-8f5b-e90bd6c77476"
       }
    }

You can also obtain the same information in text format using the ``--output text`` option.

Command::

   aws redshift describe-clusters --output text

Result::

    dw.hs1.xlarge	1.0	true	adminuser	True	us-east-1a	2013-01-22T21:59:29.559Z	sat:03:30-sat:04:00	1	available	mycluster	dev	2
    ENDPOINT	5439	mycluster.coqoarplqhsn.us-east-1.redshift.amazonaws.com
    in-sync	default.redshift-1.0
    active	default
    PENDINGMODIFIEDVALUES
    RESPONSEMETADATA	934281a8-64df-11e2-b07c-f7fbdd006c67



======
Output
======

Marker -> (string)

  

  A value that indicates the starting point for the next set of response records in a subsequent request. If a value is returned in a response, you can retrieve the next set of records by providing this returned marker value in the ``Marker`` parameter and retrying the command. If the ``Marker`` field is empty, all response records have been retrieved for the request. 

  

  

Clusters -> (list)

  

  A list of  Cluster objects, where each object describes one cluster. 

  

  (structure)

    

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
