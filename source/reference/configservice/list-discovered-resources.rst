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
  [--next-token <value>]
  [--cli-input-json <value>]
  [--generate-cli-skeleton]




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

  

``--next-token`` (string)


  The ``nextToken`` string returned on a previous page that you use to get the next page of results in a paginated response.

  

``--cli-input-json`` (string)
Performs service operation based on the JSON string provided. The JSON string follows the format provided by ``--generate-cli-skeleton``. If other arguments are provided on the command line, the CLI values will override the JSON-provided values.

``--generate-cli-skeleton`` (boolean)
Prints a sample input JSON to standard output. Note the specified operation is not run if this argument is specified. The sample input can be used as an argument for ``--cli-input-json``.



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

  

  

