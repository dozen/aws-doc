[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift describe-cluster-versions:


*************************
describe-cluster-versions
*************************



===========
Description
===========



Returns descriptions of the available Amazon Redshift cluster versions. You can call this operation even before creating any clusters to learn more about the Amazon Redshift versions. For more information about managing clusters, go to `Amazon Redshift Clusters`_ in the *Amazon Redshift Cluster Management Guide*  



``describe-cluster-versions`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``ClusterVersions``


========
Synopsis
========

::

    describe-cluster-versions
  [--cluster-version <value>]
  [--cluster-parameter-group-family <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton]




=======
Options
=======

``--cluster-version`` (string)


  The specific cluster version to return. 

   

  Example: ``1.0`` 

  

``--cluster-parameter-group-family`` (string)


  The name of a specific cluster parameter group family to return details for. 

   

  Constraints:

   

   
  * Must be 1 to 255 alphanumeric characters
   
  * First character must be a letter
   
  * Cannot end with a hyphen or contain two consecutive hyphens
   

  

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

Get a Description of All Cluster Versions
-----------------------------------------

This example returns a description of all cluster versions.  By default, the output is in JSON format.

Command::

   aws redshift describe-cluster-versions

Result::

    {
       "ClusterVersions": [
          {
          "ClusterVersion": "1.0",
          "Description": "Initial release",
          "ClusterParameterGroupFamily": "redshift-1.0"
          } ],
       "ResponseMetadata": {
          "RequestId": "16a53de3-64cc-11e2-bec0-17624ad140dd"
       }
    }



======
Output
======

Marker -> (string)

  

  A value that indicates the starting point for the next set of response records in a subsequent request. If a value is returned in a response, you can retrieve the next set of records by providing this returned marker value in the ``Marker`` parameter and retrying the command. If the ``Marker`` field is empty, all response records have been retrieved for the request. 

  

  

ClusterVersions -> (list)

  

  A list of ``Version`` elements. 

  

  (structure)

    

    Describes a cluster version, including the parameter group family and description of the version.

    

    ClusterVersion -> (string)

      

      The version number used by the cluster. 

      

      

    ClusterParameterGroupFamily -> (string)

      

      The name of the cluster parameter group family for the cluster. 

      

      

    Description -> (string)

      

      The description of the cluster version. 

      

      

    

  



.. _Amazon Redshift Clusters: http://docs.aws.amazon.com/redshift/latest/mgmt/working-with-clusters.html
