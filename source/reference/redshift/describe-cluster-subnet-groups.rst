[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift describe-cluster-subnet-groups:


******************************
describe-cluster-subnet-groups
******************************



===========
Description
===========



Returns one or more cluster subnet group objects, which contain metadata about your cluster subnet groups. By default, this operation returns information about all cluster subnet groups that are defined in you AWS account. 

 

If you specify both tag keys and tag values in the same request, Amazon Redshift returns all subnet groups that match any combination of the specified keys and values. For example, if you have ``owner`` and ``environment`` for tag keys, and ``admin`` and ``test`` for tag values, all subnet groups that have any combination of those values are returned.

 

If both tag keys and values are omitted from the request, subnet groups are returned regardless of whether they have tag keys or values associated with them.



``describe-cluster-subnet-groups`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``ClusterSubnetGroups``


========
Synopsis
========

::

    describe-cluster-subnet-groups
  [--cluster-subnet-group-name <value>]
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

``--cluster-subnet-group-name`` (string)


  The name of the cluster subnet group for which information is requested. 

  

``--tag-keys`` (list)


  A tag key or keys for which you want to return all matching cluster subnet groups that are associated with the specified key or keys. For example, suppose that you have subnet groups that are tagged with keys called ``owner`` and ``environment`` . If you specify both of these tag keys in the request, Amazon Redshift returns a response with the subnet groups that have either or both of these tag keys associated with them.

  



Syntax::

  "string" "string" ...



``--tag-values`` (list)


  A tag value or values for which you want to return all matching cluster subnet groups that are associated with the specified tag value or values. For example, suppose that you have subnet groups that are tagged with values called ``admin`` and ``test`` . If you specify both of these tag values in the request, Amazon Redshift returns a response with the subnet groups that have either or both of these tag values associated with them.

  



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

Get a Description of All Cluster Subnet Groups
----------------------------------------------

This example returns a description of all cluster subnet groups.  By default, the output is in JSON format.

Command::

   aws redshift describe-cluster-subnet-groups

Result::

    {
       "ClusterSubnetGroups": [
          {
             "Subnets": [
                {
                   "SubnetStatus": "Active",
                   "SubnetIdentifier": "subnet-763fdd1c",
                   "SubnetAvailabilityZone": {
                      "Name": "us-east-1a"
                   }
                }
             ],
             "VpcId": "vpc-7e3fdd14",
             "SubnetGroupStatus": "Complete",
             "Description": "My subnet group",
             "ClusterSubnetGroupName": "mysubnetgroup"
          }
       ],
       "ResponseMetadata": {
          "RequestId": "37fa8c89-6990-11e2-8f75-ab4018764c77"
       }
    }



======
Output
======

Marker -> (string)

  

  A value that indicates the starting point for the next set of response records in a subsequent request. If a value is returned in a response, you can retrieve the next set of records by providing this returned marker value in the ``Marker`` parameter and retrying the command. If the ``Marker`` field is empty, all response records have been retrieved for the request. 

  

  

ClusterSubnetGroups -> (list)

  

  A list of  ClusterSubnetGroup instances. 

  

  (structure)

    

    Describes a subnet group.

    

    ClusterSubnetGroupName -> (string)

      

      The name of the cluster subnet group. 

      

      

    Description -> (string)

      

      The description of the cluster subnet group. 

      

      

    VpcId -> (string)

      

      The VPC ID of the cluster subnet group. 

      

      

    SubnetGroupStatus -> (string)

      

      The status of the cluster subnet group. Possible values are ``Complete`` , ``Incomplete`` and ``Invalid`` . 

      

      

    Subnets -> (list)

      

      A list of the VPC  Subnet elements. 

      

      (structure)

        

        Describes a subnet. 

        

        SubnetIdentifier -> (string)

          

          The identifier of the subnet. 

          

          

        SubnetAvailabilityZone -> (structure)

          

          Describes an availability zone. 

          

          Name -> (string)

            

            The name of the availability zone. 

            

            

          

        SubnetStatus -> (string)

          

          The status of the subnet. 

          

          

        

      

    Tags -> (list)

      

      The list of tags for the cluster subnet group.

      

      (structure)

        

        A tag consisting of a name/value pair for a resource.

        

        Key -> (string)

          

          The key, or name, for the resource tag.

          

          

        Value -> (string)

          

          The value for the resource tag.

          

          

        

      

    

  

