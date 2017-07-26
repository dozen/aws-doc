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
  [--limit <value>]
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




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

  

  

``--limit`` (integer)


  The maximum number of configuration items returned on each page. The default is 10. You cannot specify a limit greater than 100. If you specify 0, AWS Config uses the default.

  

``--next-token`` (string)


  The ``nextToken`` string returned on a previous page that you use to get the next page of results in a paginated response.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

     

    .. note::

       

      Currently, the list does not contain information about non-AWS components (for example, applications on your Amazon EC2 instances).

       

    

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

      

      Unique MD5 hash that represents the configuration items state.

       

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

       

      A populated field indicates that the current configuration was initiated by the events recorded in the CloudTrail log. For more information about CloudTrail, see `What is AWS CloudTrail?`_ .

       

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

      

      

    

  

nextToken -> (string)

  

  The string that you use in a subsequent request to get the next page of results in a paginated response.

  

  



.. _What is AWS CloudTrail?: http://docs.aws.amazon.com/awscloudtrail/latest/userguide/what_is_cloud_trail_top_level.html
