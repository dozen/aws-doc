[ :ref:`aws <cli:aws>` . :ref:`configservice <cli:aws configservice>` ]

.. _cli:aws configservice list-discovered-resources:


*************************
list-discovered-resources
*************************



===========
Description
===========



Accepts a resource type and returns a list of resource identifiers for the resources of that type. A resource identifier includes the resource type, ID, and (if available) the custom resource name. The results consist of resources that AWS Config has discovered, including those that AWS Config is not currently recording. You can narrow the results to include only resources that have specific resource IDs or a resource name.

 

.. note::

   

  You can specify either resource IDs or a resource name but not both in the same request.

   

 

The response is paginated, and by default AWS Config lists 100 resource identifiers on each page. You can customize this number with the ``limit`` parameter. The response includes a ``nextToken`` string, and to get the next page of results, run the request again and enter this string for the ``nextToken`` parameter.



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/config-2014-11-12/ListDiscoveredResources>`_


``list-discovered-resources`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``resourceIdentifiers``


========
Synopsis
========

::

    list-discovered-resources
  --resource-type <value>
  [--resource-ids <value>]
  [--resource-name <value>]
  [--limit <value>]
  [--include-deleted-resources | --no-include-deleted-resources]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-type`` (string)


  The type of resources that you want AWS Config to list in the response.

  

  Possible values:

  
  *   ``AWS::EC2::CustomerGateway``

  
  *   ``AWS::EC2::EIP``

  
  *   ``AWS::EC2::Host``

  
  *   ``AWS::EC2::Instance``

  
  *   ``AWS::EC2::InternetGateway``

  
  *   ``AWS::EC2::NetworkAcl``

  
  *   ``AWS::EC2::NetworkInterface``

  
  *   ``AWS::EC2::RouteTable``

  
  *   ``AWS::EC2::SecurityGroup``

  
  *   ``AWS::EC2::Subnet``

  
  *   ``AWS::CloudTrail::Trail``

  
  *   ``AWS::EC2::Volume``

  
  *   ``AWS::EC2::VPC``

  
  *   ``AWS::EC2::VPNConnection``

  
  *   ``AWS::EC2::VPNGateway``

  
  *   ``AWS::IAM::Group``

  
  *   ``AWS::IAM::Policy``

  
  *   ``AWS::IAM::Role``

  
  *   ``AWS::IAM::User``

  
  *   ``AWS::ACM::Certificate``

  
  *   ``AWS::RDS::DBInstance``

  
  *   ``AWS::RDS::DBSubnetGroup``

  
  *   ``AWS::RDS::DBSecurityGroup``

  
  *   ``AWS::RDS::DBSnapshot``

  
  *   ``AWS::RDS::EventSubscription``

  
  *   ``AWS::ElasticLoadBalancingV2::LoadBalancer``

  
  *   ``AWS::S3::Bucket``

  
  *   ``AWS::SSM::ManagedInstanceInventory``

  
  *   ``AWS::Redshift::Cluster``

  
  *   ``AWS::Redshift::ClusterSnapshot``

  
  *   ``AWS::Redshift::ClusterParameterGroup``

  
  *   ``AWS::Redshift::ClusterSecurityGroup``

  
  *   ``AWS::Redshift::ClusterSubnetGroup``

  
  *   ``AWS::Redshift::EventSubscription``

  
  *   ``AWS::CloudWatch::Alarm``

  

  

``--resource-ids`` (list)


  The IDs of only those resources that you want AWS Config to list in the response. If you do not specify this parameter, AWS Config lists all resources of the specified type that it has discovered.

  



Syntax::

  "string" "string" ...



``--resource-name`` (string)


  The custom name of only those resources that you want AWS Config to list in the response. If you do not specify this parameter, AWS Config lists all resources of the specified type that it has discovered.

  

``--limit`` (integer)


  The maximum number of resource identifiers returned on each page. The default is 100. You cannot specify a limit greater than 100. If you specify 0, AWS Config uses the default.

  

``--include-deleted-resources`` | ``--no-include-deleted-resources`` (boolean)


  Specifies whether AWS Config includes deleted resources in the results. By default, deleted resources are not included.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``next-token`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``next-token`` is provided in the command's output. To resume pagination, provide the ``next-token`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``next-token`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To list resources that AWS Config has discovered**

The following command lists the EC2 instances that AWS Config has discovered::

    aws configservice list-discovered-resources --resource-type AWS::EC2::Instance

Output::

    {
        "resourceIdentifiers": [
            {
                "resourceType": "AWS::EC2::Instance",
                "resourceId": "i-1a2b3c4d"
            },
            {
                "resourceType": "AWS::EC2::Instance",
                "resourceId": "i-2a2b3c4d"
            },
            {
                "resourceType": "AWS::EC2::Instance",
                "resourceId": "i-3a2b3c4d"
            }
        ]
    }

======
Output
======

resourceIdentifiers -> (list)

  

  The details that identify a resource that is discovered by AWS Config, including the resource type, ID, and (if available) the custom resource name.

  

  (structure)

    

    The details that identify a resource that is discovered by AWS Config, including the resource type, ID, and (if available) the custom resource name.

    

    resourceType -> (string)

      

      The type of resource.

      

      

    resourceId -> (string)

      

      The ID of the resource (for example., ``sg-xxxxxx`` ).

      

      

    resourceName -> (string)

      

      The custom name of the resource (if available).

      

      

    resourceDeletionTime -> (timestamp)

      

      The time that the resource was deleted.

      

      

    

  

nextToken -> (string)

  

  The string that you use in a subsequent request to get the next page of results in a paginated response.

  

  

