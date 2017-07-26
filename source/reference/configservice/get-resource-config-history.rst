[ :ref:`aws <cli:aws>` . :ref:`configservice <cli:aws configservice>` ]

.. _cli:aws configservice get-resource-config-history:


***************************
get-resource-config-history
***************************



===========
Description
===========



Returns a list of configuration items for the specified resource. The list contains details about each state of the resource during the specified time interval.

 

The response is paginated, and by default, AWS Config returns a limit of 10 configuration items per page. You can customize this number with the ``limit`` parameter. The response includes a ``nextToken`` string, and to get the next page of results, run the request again and enter this string for the ``nextToken`` parameter.

 

.. note::

   

  Each call to the API is limited to span a duration of seven days. It is likely that the number of records returned is smaller than the specified ``limit`` . In such cases, you can make another call, using the ``nextToken`` .

   



See also: `AWS API Documentation <https://docs.aws.amazon.com/goto/WebAPI/config-2014-11-12/GetResourceConfigHistory>`_


``get-resource-config-history`` is a paginated operation. Multiple API calls may be issued in order to retrieve the entire data set of results. You can disable pagination by providing the ``--no-paginate`` argument.
When using ``--output text`` and the ``--query`` argument on a paginated response, the ``--query`` argument must extract data from the results of the following query expressions: ``configurationItems``


========
Synopsis
========

::

    get-resource-config-history
  --resource-type <value>
  --resource-id <value>
  [--later-time <value>]
  [--earlier-time <value>]
  [--chronological-order <value>]
  [--cli-input-json <value>]
  [--starting-token <value>]
  [--page-size <value>]
  [--max-items <value>]
  [--generate-cli-skeleton <value>]




=======
Options
=======

``--resource-type`` (string)


  The resource type.

  

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

  

  

``--resource-id`` (string)


  The ID of the resource (for example., ``sg-xxxxxx`` ).

  

``--later-time`` (timestamp)


  The time stamp that indicates a later time. If not specified, current time is taken.

  

``--earlier-time`` (timestamp)


  The time stamp that indicates an earlier time. If not specified, the action returns paginated results that contain configuration items that start from when the first configuration item was recorded.

  

``--chronological-order`` (string)


  The chronological order for configuration items listed. By default the results are listed in reverse chronological order.

  

  Possible values:

  
  *   ``Reverse``

  
  *   ``Forward``

  

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--starting-token`` (string)
 

  A token to specify where to start paginating. This is the ``next-token`` from a previously truncated response.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--page-size`` (integer)
 

  The size of each page to get in the AWS service call. This does not affect the number of items returned in the command's output. Setting a smaller page size results in more calls to the AWS service, retrieving fewer items in each call. This can help prevent the AWS service calls from timing out.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--max-items`` (integer)
 

  The total number of items to return in the command's output. If the total number of items available is more than the value specified, a ``next-token`` is provided in the command's output. To resume pagination, provide the ``next-token`` value in the ``starting-token`` argument of a subsequent command. **Do not** use the ``next-token`` response element directly outside of the AWS CLI.

   

  For usage examples, see `Pagination <https://docs.aws.amazon.com/cli/latest/userguide/pagination.html>`_ in the *AWS Command Line Interface User Guide* .

   

``--generate-cli-skeleton`` (string)
Prints a JSON skeleton to standard output without sending an API request. If provided with no value or the value ``input``, prints a sample input JSON that can be used as an argument for ``--cli-input-json``. If provided with the value ``output``, it validates the command inputs and returns a sample output JSON for that command.



========
Examples
========

**To get the configuration history of an AWS resource**

The following command returns a list of configuration items for an EC2 instance with an ID of ``i-1a2b3c4d``::

    aws configservice get-resource-config-history --resource-type AWS::EC2::Instance --resource-id i-1a2b3c4d

======
Output
======

configurationItems -> (list)

  

  A list that contains the configuration history of one or more resources.

  

  (structure)

    

    A list that contains detailed configurations of a specified resource.

    

    version -> (string)

      

      The version number of the resource configuration.

      

      

    accountId -> (string)

      

      The 12 digit AWS account ID associated with the resource.

      

      

    configurationItemCaptureTime -> (timestamp)

      

      The time when the configuration recording was initiated.

      

      

    configurationItemStatus -> (string)

      

      The configuration item status.

      

      

    configurationStateId -> (string)

      

      An identifier that indicates the ordering of the configuration items of a resource.

      

      

    configurationItemMD5Hash -> (string)

      

      Unique MD5 hash that represents the configuration item's state.

       

      You can use MD5 hash to compare the states of two or more configuration items that are associated with the same resource.

      

      

    arn -> (string)

      

      The Amazon Resource Name (ARN) of the resource.

      

      

    resourceType -> (string)

      

      The type of AWS resource.

      

      

    resourceId -> (string)

      

      The ID of the resource (for example., ``sg-xxxxxx`` ).

      

      

    resourceName -> (string)

      

      The custom name of the resource, if available.

      

      

    awsRegion -> (string)

      

      The region where the resource resides.

      

      

    availabilityZone -> (string)

      

      The Availability Zone associated with the resource.

      

      

    resourceCreationTime -> (timestamp)

      

      The time stamp when the resource was created.

      

      

    tags -> (map)

      

      A mapping of key value tags associated with the resource.

      

      key -> (string)

        

        

      value -> (string)

        

        

      

    relatedEvents -> (list)

      

      A list of CloudTrail event IDs.

       

      A populated field indicates that the current configuration was initiated by the events recorded in the CloudTrail log. For more information about CloudTrail, see `What is AWS CloudTrail? <http://docs.aws.amazon.com/awscloudtrail/latest/userguide/what_is_cloud_trail_top_level.html>`_ .

       

      An empty field indicates that the current configuration was not initiated by any event.

      

      (string)

        

        

      

    relationships -> (list)

      

      A list of related AWS resources.

      

      (structure)

        

        The relationship of the related resource to the main resource.

        

        resourceType -> (string)

          

          The resource type of the related resource.

          

          

        resourceId -> (string)

          

          The ID of the related resource (for example, ``sg-xxxxxx`` ).

          

          

        resourceName -> (string)

          

          The custom name of the related resource, if available.

          

          

        relationshipName -> (string)

          

          The type of relationship with the related resource.

          

          

        

      

    configuration -> (string)

      

      The description of the resource configuration.

      

      

    supplementaryConfiguration -> (map)

      

      Configuration attributes that AWS Config returns for certain resource types to supplement the information returned for the ``configuration`` parameter.

      

      key -> (string)

        

        

      value -> (string)

        

        

      

    

  

nextToken -> (string)

  

  The string that you use in a subsequent request to get the next page of results in a paginated response.

  

  

