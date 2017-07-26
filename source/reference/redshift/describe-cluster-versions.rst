[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift describe-cluster-versions:


*************************
describe-cluster-versions
*************************



===========
Description
===========



Returns descriptions of the available Amazon Redshift cluster versions. You can call this operation even before creating any clusters to learn more about the Amazon Redshift versions. For more information about managing clusters, go to `Amazon Redshift Clusters <http://docs.aws.amazon.com/redshift/latest/mgmt/working-with-clusters.html>`_ in the *Amazon Redshift Cluster Management Guide* .



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/redshift-2012-12-01/DescribeClusterVersions>`_


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
  [--generate-cli-skeleton <value>]




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

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``NextToken`` is provided in the command's output. To resume pagination, provide the ``NextToken`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``NextToken`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



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

      

      

    

  

