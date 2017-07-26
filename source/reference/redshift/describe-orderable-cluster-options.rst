[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift describe-orderable-cluster-options:


**********************************
describe-orderable-cluster-options
**********************************



===========
Description
===========



Returns a list of orderable cluster options. Before you create a new cluster you can use this operation to find what options are available, such as the EC2 Availability Zones (AZ) in the specific AWS region that you can specify, and the node types you can request. The node types differ by available storage, memory, CPU and price. With the cost involved you might want to obtain a list of cluster options in the specific region and specify values when creating a cluster. For more information about managing clusters, go to `Amazon Redshift Clusters`_ in the *Amazon Redshift Cluster Management Guide*  



``describe-orderable-cluster-options`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``OrderableClusterOptions``


========
Synopsis
========

::

    describe-orderable-cluster-options
  [--cluster-version <value>]
  [--node-type <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cluster-version`` (string)


  The version filter value. Specify this parameter to show only the available offerings matching the specified version. 

   

  Default: All versions.

   

  Constraints: Must be one of the version returned from  describe-cluster-versions .

  

``--node-type`` (string)


  The node type filter value. Specify this parameter to show only the available offerings matching the specified node type. 

  

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

Describing All Orderable Cluster Options
----------------------------------------

This example returns descriptions of all orderable cluster options.  By default, the output is in JSON format.

Command::

   aws redshift describe-orderable-cluster-options

Result::

    {
       "OrderableClusterOptions": [
          {
             "NodeType": "dw.hs1.8xlarge",
             "AvailabilityZones": [
                { "Name": "us-east-1a" },
                { "Name": "us-east-1b" },
                { "Name": "us-east-1c" } ],
             "ClusterVersion": "1.0",
             "ClusterType": "multi-node"
          },
          {
             "NodeType": "dw.hs1.xlarge",
             "AvailabilityZones": [
                { "Name": "us-east-1a" },
                { "Name": "us-east-1b" },
                { "Name": "us-east-1c" } ],
             "ClusterVersion": "1.0",
             "ClusterType": "multi-node"
          },
          {
          "NodeType": "dw.hs1.xlarge",
          "AvailabilityZones": [
             { "Name": "us-east-1a" },
             { "Name": "us-east-1b" },
             { "Name": "us-east-1c" } ],
          "ClusterVersion": "1.0",
          "ClusterType": "single-node"
          } ],
       "ResponseMetadata": {
          "RequestId": "f6000035-64cb-11e2-9135-ff82df53a51a"
       }
    }

You can also obtain the same information in text format using the ``--output text`` option.

Command::

   aws redshift describe-orderable-cluster-options --output text

Result::

    dw.hs1.8xlarge	1.0	multi-node
    us-east-1a
    us-east-1b
    us-east-1c
    dw.hs1.xlarge	1.0	multi-node
    us-east-1a
    us-east-1b
    us-east-1c
    dw.hs1.xlarge	1.0	single-node
    us-east-1a
    us-east-1b
    us-east-1c
    RESPONSEMETADATA	e648696b-64cb-11e2-bec0-17624ad140dd




======
Output
======

OrderableClusterOptions -> (list)

  

  An  OrderableClusterOption structure containing information about orderable options for the Cluster.

  

  (structure)

    

    Describes an orderable cluster option. 

    

    ClusterVersion -> (string)

      

      The version of the orderable cluster. 

      

      

    ClusterType -> (string)

      

      The cluster type, for example ``multi-node`` . 

      

      

    NodeType -> (string)

      

      The node type for the orderable cluster. 

      

      

    AvailabilityZones -> (list)

      

      A list of availability zones for the orderable cluster. 

      

      (structure)

        

        Describes an availability zone. 

        

        Name -> (string)

          

          The name of the availability zone. 

          

          

        

      

    

  

Marker -> (string)

  

  A value that indicates the starting point for the next set of response records in a subsequent request. If a value is returned in a response, you can retrieve the next set of records by providing this returned marker value in the ``Marker`` parameter and retrying the command. If the ``Marker`` field is empty, all response records have been retrieved for the request. 

  

  



.. _Amazon Redshift Clusters: http://docs.aws.amazon.com/redshift/latest/mgmt/working-with-clusters.html
