[ :ref:`aws <cli:aws>` . :ref:`redshift <cli:aws redshift>` ]

.. _cli:aws redshift describe-cluster-security-groups:


********************************
describe-cluster-security-groups
********************************



===========
Description
===========



Returns information about Amazon Redshift security groups. If the name of a security group is specified, the response will contain only information about only that security group.

 

For information about managing security groups, go to `Amazon Redshift Cluster Security Groups <http://docs.aws.amazon.com/redshift/latest/mgmt/working-with-security-groups.html>`_ in the *Amazon Redshift Cluster Management Guide* .

 

If you specify both tag keys and tag values in the same request, Amazon Redshift returns all security groups that match any combination of the specified keys and values. For example, if you have ``owner`` and ``environment`` for tag keys, and ``admin`` and ``test`` for tag values, all security groups that have any combination of those values are returned.

 

If both tag keys and values are omitted from the request, security groups are returned regardless of whether they have tag keys or values associated with them.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/redshift-2012-12-01/DescribeClusterSecurityGroups>`_


``describe-cluster-security-groups`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``ClusterSecurityGroups``


========
Synopsis
========

::

    describe-cluster-security-groups
  [--cluster-security-group-name <value>]
  [--tag-keys <value>]
  [--tag-values <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--cluster-security-group-name`` (string)


  The name of a cluster security group for which you are requesting details. You can specify either the **Marker** parameter or a **ClusterSecurityGroupName** parameter, but not both. 

   

  Example: ``securitygroup1``  

  

``--tag-keys`` (list)


  A tag key or keys for which you want to return all matching cluster security groups that are associated with the specified key or keys. For example, suppose that you have security groups that are tagged with keys called ``owner`` and ``environment`` . If you specify both of these tag keys in the request, Amazon Redshift returns a response with the security groups that have either or both of these tag keys associated with them.

  



Syntax::

  "string" "string" ...



``--tag-values`` (list)


  A tag value or values for which you want to return all matching cluster security groups that are associated with the specified tag value or values. For example, suppose that you have security groups that are tagged with values called ``admin`` and ``test`` . If you specify both of these tag values in the request, Amazon Redshift returns a response with the security groups that have either or both of these tag values associated with them.

  



Syntax::

  "string" "string" ...



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

Get a Description of All Cluster Security Groups
------------------------------------------------

This example returns a description of all cluster security groups for the account.
By default, the output is in JSON format.

Command::

   aws redshift describe-cluster-security-groups

Result::

    {
       "ClusterSecurityGroups": [
          {
             "OwnerId": "100447751468",
             "Description": "default",
             "ClusterSecurityGroupName": "default",
             "EC2SecurityGroups": \[],
             "IPRanges": [
                {
                   "Status": "authorized",
                   "CIDRIP": "0.0.0.0/0"
                }
             ]
          },
          {
             "OwnerId": "100447751468",
             "Description": "This is my cluster security group",
             "ClusterSecurityGroupName": "mysecuritygroup",
             "EC2SecurityGroups": \[],
             "IPRanges": \[]
          },
          (...remaining output omitted...)
       ]
    }



======
Output
======

Marker -> (string)

  

  A value that indicates the starting point for the next set of response records in a subsequent request. If a value is returned in a response, you can retrieve the next set of records by providing this returned marker value in the ``Marker`` parameter and retrying the command. If the ``Marker`` field is empty, all response records have been retrieved for the request. 

  

  

ClusterSecurityGroups -> (list)

  

  A list of  ClusterSecurityGroup instances. 

  

  (structure)

    

    Describes a security group.

    

    ClusterSecurityGroupName -> (string)

      

      The name of the cluster security group to which the operation was applied.

      

      

    Description -> (string)

      

      A description of the security group.

      

      

    EC2SecurityGroups -> (list)

      

      A list of EC2 security groups that are permitted to access clusters associated with this cluster security group.

      

      (structure)

        

        Describes an Amazon EC2 security group.

        

        Status -> (string)

          

          The status of the EC2 security group.

          

          

        EC2SecurityGroupName -> (string)

          

          The name of the EC2 Security Group.

          

          

        EC2SecurityGroupOwnerId -> (string)

          

          The AWS ID of the owner of the EC2 security group specified in the ``EC2SecurityGroupName`` field. 

          

          

        Tags -> (list)

          

          The list of tags for the EC2 security group.

          

          (structure)

            

            A tag consisting of a name/value pair for a resource.

            

            Key -> (string)

              

              The key, or name, for the resource tag.

              

              

            Value -> (string)

              

              The value for the resource tag.

              

              

            

          

        

      

    IPRanges -> (list)

      

      A list of IP ranges (CIDR blocks) that are permitted to access clusters associated with this cluster security group.

      

      (structure)

        

        Describes an IP range used in a security group.

        

        Status -> (string)

          

          The status of the IP range, for example, "authorized".

          

          

        CIDRIP -> (string)

          

          The IP range in Classless Inter-Domain Routing (CIDR) notation.

          

          

        Tags -> (list)

          

          The list of tags for the IP range.

          

          (structure)

            

            A tag consisting of a name/value pair for a resource.

            

            Key -> (string)

              

              The key, or name, for the resource tag.

              

              

            Value -> (string)

              

              The value for the resource tag.

              

              

            

          

        

      

    Tags -> (list)

      

      The list of tags for the cluster security group.

      

      (structure)

        

        A tag consisting of a name/value pair for a resource.

        

        Key -> (string)

          

          The key, or name, for the resource tag.

          

          

        Value -> (string)

          

          The value for the resource tag.

          

          

        

      

    

  

